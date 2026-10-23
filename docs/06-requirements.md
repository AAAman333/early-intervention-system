# Requirements Specification


- **FR** — functional requirement (what the system does). **NFR** — non-functional requirement (how well it does it: security, speed, usability).
- Priorities use MoSCoW: **Must** (required for the final prototype), **Should** (important), **Could** (if time allows), **Won't** (out of scope).
- **Stage** shows when the requirement is planned to be implemented (see section 5). Pre-defense 1 includes analysis and design only, no code.
- Requirements marked *(assumption)* must be confirmed in interviews (see `02-relevance.md`).


## 1. User roles

| Role | Description |
|---|---|
| **Parent** | Registers, creates and owns the profile of their child, connects to a specialist and gives them access to the child's data, follows the plan, schedule and progress |
| **Specialist** | Early intervention specialist (speech therapist, psychologist, physical therapist, etc.). Accepts children, creates individual plans, schedules sessions, records attendance and progress |
| **Administrator** | Verifies specialists, manages the catalog of session types, monitors the system and views summary reports |
| **Child** | A user of the system whose account is created, filled in and managed by the parent. The child does not log in; the parent opens the child's account and decides which specialists can see it. Added after the supervisor's feedback (23.10.2026) |

**Key principle:** the child's data belongs to the parent. A specialist sees a child only after the parent has shared access, and the parent can revoke it.

## 2. Functional requirements

### 2.1 Accounts and access

| ID | Requirement | Priority | Stage | Acceptance criteria |
|---|---|---|---|---|
| FR-01 | Parents and specialists register with email and password; all users log in | Must | 2 | Registration creates an account; login with valid data works, invalid data shows an error |
| FR-02 | The system has three account roles (parent, specialist, administrator) and child users managed by parents (FR-37) | Must | 2 | Available pages and actions depend on the role |
| FR-03 | A specialist account is active only after verification by the administrator | Must | 2 | An unverified specialist cannot accept children; the administrator sees a list of pending specialists |
| FR-04 | Users can edit their profile; specialists add specialisation and experience | Should | 2 | Changes are saved and shown in the profile |

### 2.2 Child profile (parent)

| ID | Requirement | Priority | Stage | Acceptance criteria |
|---|---|---|---|---|
| FR-05 | Parent creates a child profile: name, date of birth, diagnosis or concerns, notes | Must | 2 | The profile is saved in the parent's account |
| FR-06 | Parent can have several children in one account | Should | 2 | Each child has a separate profile |
| FR-07 | Parent uploads documents to the child profile (conclusions, medical reports) | Could | 3 | A file up to 10 MB can be uploaded and downloaded *(assumption)* |

### 2.3 Connecting to a specialist and data sharing

| ID | Requirement | Priority | Stage | Acceptance criteria |
|---|---|---|---|---|
| FR-08 | Parent searches verified specialists (see also FR-33, FR-34) | Must | 2 | Only verified specialists appear in search results |
| FR-09 | Parent sends a request to a specialist and gives access to the selected child profile | Must | 2 | The specialist receives the request with the child's data |
| FR-10 | Specialist accepts or rejects the request | Must | 2 | After acceptance the child appears in the specialist's list; after rejection the specialist has no access |
| FR-11 | Parent can revoke a specialist's access at any time | Must | 2 | After revoking, the specialist cannot open the child's data; the history of held sessions is kept |
| FR-12 | A specialist sees only children who shared access with them | Must | 2 | A request to another child's data returns "access denied" |
| FR-13 | Several specialists can work with one child; each sees the common history | Should | 3 | All connected specialists see the child's plans and sessions |

### 2.4 Individual plans (specialist)

| ID | Requirement | Priority | Stage | Acceptance criteria |
|---|---|---|---|---|
| FR-14 | Specialist creates an individual plan: period, goals, session types, intensity (sessions per week) | Must | 2 | The plan is saved and shown to the specialist and the parent |
| FR-15 | Plan has a status: draft, active, completed, cancelled | Must | 2 | Only active plans can have scheduled sessions; parents do not see drafts |
| FR-16 | Administrator manages the catalog of session types | Must | 2 | Specialists choose session types from the catalog |
| FR-17 | Changes to a plan are recorded in history | Should | 3 | The plan shows who changed what and when |

### 2.5 Scheduling

| ID | Requirement | Priority | Stage | Acceptance criteria |
|---|---|---|---|---|
| FR-18 | Specialist schedules sessions, including weekly recurring sessions | Must | 3 | Recurrence creates a session for each week of the plan period |
| FR-19 | The system prevents overlapping sessions for one specialist | Must | 3 | An overlapping session is not saved and a warning is shown |
| FR-20 | Specialist reschedules or cancels a session with a reason | Must | 3 | The change is saved and visible to the parent |
| FR-21 | Parent and specialist see a calendar of sessions (day / week) | Must | 3 | Each user sees only their own or their child's sessions |

### 2.6 Attendance and progress

| ID | Requirement | Priority | Stage | Acceptance criteria |
|---|---|---|---|---|
| FR-22 | Specialist marks a session as held, missed (with reason) or cancelled | Must | 3 | The status is shown in the calendar and history |
| FR-23 | Specialist adds a comment and recommendations for home after a session | Must | 3 | The parent sees the comment in the child's history |
| FR-24 | Specialist records progress on goals (not started / in progress / achieved) | Should | 3 | Goal status and change history are visible to the parent |
| FR-25 | Child's page shows the full history of sessions in chronological order | Must | 3 | All sessions of the child are listed with status and comments |

### 2.7 Reports and notifications

| ID | Requirement | Priority | Stage | Acceptance criteria |
|---|---|---|---|---|
| FR-26 | Report on plan execution: planned vs held sessions and attendance rate for a period | Must | 3 | Numbers match the sessions in the database |
| FR-27 | Administrator sees summary statistics: number of users, active plans, sessions | Should | 3 | Numbers match the database |
| FR-28 | Push reminders to parents about upcoming sessions in the mobile app | Could | 3 | A push notification arrives before the session *(assumption)* |
| FR-29 | Export of reports to PDF | Could | 3 | The file contains the same data as the screen |
| FR-30 | Online payment, video sessions, integration with state information systems | Won't | — | Out of scope |

### 2.8 Smart features: screening and specialist search

| ID | Requirement | Priority | Stage | Acceptance criteria |
|---|---|---|---|---|
| FR-31 | Parent completes an age-based developmental milestone checklist in the app (based on CDC evidence-informed milestones) | Should | 3 | The checklist matches the child's age; answers are saved in the child profile |
| FR-32 | The system shows the result by domain (speech, motor, social, self-care) and recommends which type of specialist to consult; it clearly states that it is not a diagnosis | Should | 3 | For a test answer set with missed speech milestones, the result recommends a speech therapist and shows the disclaimer |
| FR-33 | Parent searches specialists by city and specialisation | Must | 2 | Only verified specialists from the selected city are shown |
| FR-34 | Search results are ranked by a weighted score: specialisation match, average rating and nearest free time slot | Should | 3 | For test data the order matches the score calculated by hand |
| FR-35 | After at least one held session, a parent can rate the specialist by several criteria (communication, results, punctuality) and leave a review | Should | 3 | The rating is shown in the specialist profile; a parent without held sessions cannot rate |
| FR-36 | Specialist sets weekly free time slots | Should | 3 | Free slots are used in search ranking and when sending a request |

### 2.9 Child as a user

| ID | Requirement | Priority | Stage | Acceptance criteria |
|---|---|---|---|---|
| FR-37 | Each child is a user of the system. The child's account is created and filled in by the parent (name, date of birth, concerns, documents) and is linked to one or more parents | Must | 2 | A child account cannot exist without a parent; the child appears in the parent's account and in the administrator's list of users with the linked parent |
| FR-38 | The child does not log in; only the parent opens and edits the child's account and decides which specialists can see it (see FR-09 – FR-11) | Must | 2 | There is no login form for children; a specialist sees the child's account only after the parent has shared it |

## 3. Non-functional requirements

| ID | Category | Requirement | Priority | Acceptance criteria |
|---|---|---|---|---|
| NFR-01 | Security | Passwords are stored only as hashes (bcrypt or similar) | Must | No plain-text passwords in the database |
| NFR-02 | Security | All access rules are checked on the server | Must | Requests without rights return 401/403 |
| NFR-03 | Privacy | Access to a child's data only with the parent's consent (FR-09, FR-11); consent actions are logged | Must | The log shows who granted or revoked access and when |
| NFR-04 | Privacy | The prototype uses only demonstration data, no real children's data | Must | The demo database contains only generated data |
| NFR-05 | Security | Secrets are not stored in the repository | Must | Only `.env.example` with placeholders is committed |
| NFR-06 | Performance | Main pages open in under 2 seconds with demo data (100 children, 15 specialists, 5,000 sessions) | Should | Measured on a local deployment |
| NFR-07 | Usability | A specialist records a held session in no more than 3 clicks from the calendar | Should | Checked in usability testing |
| NFR-08 | Portability | The parent app runs on Android and iOS; the specialist and admin web application works in current browsers on a laptop and tablet | Must | Parent scenarios work on an Android device / emulator and iOS simulator; web scenarios work in Chrome and Safari |
| NFR-09 | Maintainability | Core business logic is covered by automated tests | Should | Coverage of core modules ≥ 60% |
| NFR-10 | Portability | The system starts locally with one command (Docker Compose) | Should | README instructions work on a clean machine |
| NFR-11 | Localisation | Interface in Russian, optionally Kazakh and English | Could | Language can be switched *(assumption)* |

## 4. Key acceptance scenario

1. Parent registers and creates a child profile (FR-01, FR-05).
2. Parent finds a verified specialist and sends a request with access to the child (FR-08, FR-09).
3. Specialist accepts the request; the child appears in the specialist's list (FR-10).
4. Specialist creates a plan: 2 goals, 2 sessions per week for 4 weeks (FR-14, FR-15).
5. Specialist schedules recurring sessions; the calendar shows 8 sessions without overlaps (FR-18, FR-19).
6. Specialist marks 6 sessions as held with comments, 1 as missed, 1 as cancelled (FR-22, FR-23).
7. Parent sees the history and comments; the report shows planned 8, held 6, attendance 75% (FR-25, FR-26).
8. Parent revokes access; the specialist no longer sees the child (FR-11).
