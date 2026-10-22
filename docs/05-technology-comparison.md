# Technology Comparison

Each key decision compares 2–3 realistic alternatives against criteria taken from the requirements (`06-requirements.md`). Scores: 1 (poor) – 3 (good). An important practical criterion for an individual project is **the developer's experience**: I(Moldir) have experience with JavaScript/React, Node.js, Python, Java, Flutter and Swift (Xcode).

## Summary of selected stack

| Layer | Selected technology |
|---|---|
| Parent client | Flutter mobile app (Android, iOS) |
| Specialist and admin client | React web application (Vite) |
| Backend | Node.js + Express |
| Database | PostgreSQL |
| ORM / data access | Prisma |
| Client–server interaction | REST API (JSON over HTTPS) |
| Authentication | JWT (httpOnly cookie on web, secure storage in the app), bcrypt |
| Testing | Jest + Supertest (backend), flutter_test (mobile), manual test cases |
| Deployment | Docker Compose (local), free cloud hosting for the demo |

---

## Decision 1. Client platform

Requirements: three roles with different interfaces (FR-02); parents mostly use a phone (confirmed by the survey: 92% of 13 parents prefer a phone, see `02-relevance.md`); specialists and administrators work with calendars, tables and reports, mostly at a computer; optional push reminders for parents (FR-28); one developer.

Criteria about the quality for the target users have **weight ×2**, because the system is useful only if parents and specialists actually use it.

| Criterion | Weight | A. React web for all roles | B. Flutter app for parents + React web for specialists and admin | C. Flutter for all (mobile + Flutter web) |
|---|---|---|---|---|
| Convenience for parents on a phone (native app, offline login, home screen) | ×2 | 2 | 3 | 3 |
| Convenience for specialists and admin at a computer (tables, calendar, reports) | ×2 | 3 | 3 | 2 — Flutter web is heavier and less suited to data-heavy admin pages |
| Push notifications for parents (FR-28) | ×1 | 1 | 3 | 3 |
| Developer experience | ×1 | 3 | 3 | 3 |
| Development effort for one person | ×1 | 3 | 1 — two clients | 2 |
| **Weighted total** | | **17** | **19** | **18** |

**Choice: B — Flutter mobile app for parents and React web application for specialists and administrators.** Each user group gets the interface that suits how they work. The higher effort is reduced because all business logic is on the server (one REST API for both clients, Decision 4), and the parent app covers only parent functions. Flutter was chosen over native iOS (Swift) because one code base covers both Android and iOS.

## Decision 2. Server platform

Requirements: REST API with role and consent checks (FR-02, FR-12, NFR-02), business logic for scheduling and reports (FR-18 – FR-26), automated tests (NFR-09).

| Criterion | Node.js + Express | Python + Django (DRF) | Java + Spring Boot |
|---|---|---|---|
| One language with the React web client | 3 | 1 | 1 |
| Speed of development for one person | 3 — minimal setup | 3 — many built-in features | 2 — more configuration |
| Fit for REST API | 3 | 3 | 3 |
| Libraries for auth, validation, testing | 3 (Passport/JWT, Zod, Jest) | 3 | 3 |
| Developer experience | 3 | 2 | 2 |
| Built-in structure (risk of messy code) | 2 — structure must be organised manually | 3 | 3 |
| **Total** | **17** | **15** | **14** |

**Choice: Node.js + Express.** Mitigation of the weak point: code is organised by modules from the component diagram (users, children, access, plans, scheduling, attendance, reports), each with routes → service → data layers.

## Decision 3. Data storage

Requirements: strongly connected data (users, children, access grants, plans, sessions), reports with aggregation (FR-26), consistency of changes (transactions), access log (NFR-03).

| Criterion | PostgreSQL | MySQL | MongoDB |
|---|---|---|---|
| Relations and integrity (foreign keys) | 3 | 3 | 1 — no joins by design |
| Transactions | 3 | 3 | 2 |
| Reports with JOIN / GROUP BY | 3 | 3 | 2 — aggregation pipeline is more complex |
| Date / time ranges for scheduling and overlap checks | 3 — range types, exclusion constraints | 2 | 2 |
| Free hosting options | 3 | 3 | 3 |
| **Total** | **15** | **14** | **10** |

**Choice: PostgreSQL.** The data model is relational, and PostgreSQL can enforce "no overlapping sessions for one specialist" (FR-19) directly in the database.

## Decision 4. Client–server interaction

Requirements: one API for three roles and two clients (Flutter and React); simple to test.

| Criterion | REST (JSON) | GraphQL | Firebase (direct database access from client) |
|---|---|---|---|
| Simplicity for one developer | 3 | 2 | 3 |
| Access control on the server (NFR-02) | 3 — every endpoint checks rights | 3 | 2 — security rules are hard to write for consent-based access |
| Easy to test (Supertest, Postman) | 3 | 2 | 2 |
| One API for both Flutter and React clients | 3 | 3 | 3 |
| Vendor independence | 3 | 3 | 1 |
| **Total** | **15** | **13** | **11** |

**Choice: REST API.** One API serves both clients; the number of screens and data types is moderate, so GraphQL flexibility is not needed.

## Decision 5. Authentication

Requirements: login for three roles (FR-01, FR-02), secure password storage (NFR-01).

| Criterion | JWT in httpOnly cookie | Server sessions (express-session + DB) | External provider (Firebase Auth / Auth0) |
|---|---|---|---|
| Security against XSS token theft | 3 (httpOnly) | 3 | 3 |
| Works for both web and mobile clients | 3 | 2 | 3 |
| Simplicity | 2 | 3 | 2 — extra integration |
| Independence from external services | 3 | 3 | 1 |
| **Total** | **11** | **11** | **9** |

**Choice: JWT** (equal score with sessions, chosen because it works for both clients): the web application keeps the token in an httpOnly cookie, the Flutter app sends it in the Authorization header and stores it in secure storage (flutter_secure_storage). Passwords are hashed with bcrypt.

## Decision 6. Data access layer

| Criterion | Prisma | Sequelize | Plain SQL (pg) |
|---|---|---|---|
| Schema and migrations in one file | 3 | 2 | 1 |
| Type safety and autocomplete | 3 | 2 | 1 |
| Control over complex queries (reports) | 2 — raw SQL available when needed | 2 | 3 |
| Learning effort | 3 | 2 | 2 |
| **Total** | **11** | **8** | **7** |

**Choice: Prisma**, with raw SQL for complex reports if needed.

## Related decisions (short)

- **Testing:** Jest + Supertest for backend unit and API tests (NFR-09); flutter_test for key parent screens; manual test cases from `08-verification-plan.md`.
- **Push notifications (optional, FR-28):** Firebase Cloud Messaging, used only for sending notifications, not for storing data.
- **Deployment:** Docker Compose to start the database and backend with one command (NFR-10); for the demo, free hosting (e.g. Render / Railway / Vercel), to be chosen at stage 2.
- **Design of mockups:** Figma (DIP-9): mobile screens for parents, desktop screens for specialists and admin.
