# Development of a Digital System for Managing Early Intervention Programs

An information system — a mobile app for parents and a web application for specialists — that helps early intervention centres plan, schedule and track individual intervention programs for children: program goals, session types and intensity, calendar, attendance, execution history and reports.

## Problem statement

Early intervention programs are planned individually for each child: goals, types of sessions, intensity, attendance, execution and feedback. In practice this information is often kept in scattered paper records, spreadsheets and messengers. As a result, it is difficult for specialists to see the full picture of a child's program, to check whether planned sessions were actually held, and for administrators to prepare reports.

## Target users

- **Parents** — create and own the child's profile, connect to specialists and share data with them, follow the plan, schedule and progress.
- **Early intervention specialists** (psychologists, speech therapists, physical therapists, etc.) — create individual plans, schedule sessions, record attendance and comments.
- **Administrators** — verify specialists, manage the catalog of session types, monitor the system.
- **Children** — users of the system; the account is created, filled in and opened by the parent.

The prototype uses demonstration data only. Real personal data of children is not collected or stored.

## Aim and expected outcomes

**Aim:** to develop a working prototype of an information system for structured planning and tracking of individual early intervention programs.

**Expected outcomes:**
- a working prototype: Flutter mobile app for parents and web application for specialists and administrators, with role-based access;
- verifiable scenarios: parent shares child profile → specialist creates a plan and schedules sessions → attendance and comments are recorded → parent sees progress and the report;
- project documentation (requirements, architecture, test plan) and demonstration data.

## Project scope

**In scope:**
- four user types: parent, child (managed by the parent), specialist, administrator;
- child profiles owned by parents and consent-based data sharing with specialists;
- catalog of session types;
- individual intervention plans;
- calendar scheduling of sessions;
- attendance tracking and execution history;
- reports on program progress;
- functional testing of the key scenarios.

**Out of scope:**
- processing of real personal or medical data of children;
- integration with state medical information systems;
- a mobile app for specialists (they use the web application);
- online payments and video sessions.

## Team and supervisor

| Name | Role | Responsibilities |
|---|---|---|
| Yergesh Moldir Batyrbekkyzy | Student (individual project) | Analysis, requirements, design, implementation, testing, documentation |
| Basheyeva Zh.O. | Supervisor | Weekly review of progress and key deliverables |

## Current status

**Stage: analysis and design (pre-defense 1).**

The topic and scope are approved by the supervisor. Current work: project proposal, evidence of relevance, literature review, comparison of existing systems and technologies, requirements, architecture diagrams, UI prototype and verification plan.

## Technologies

Selected after comparison of alternatives (see [`docs/05-technology-comparison.md`](docs/05-technology-comparison.md)):

- **Parent client:** Flutter mobile app (Android, iOS)
- **Specialist and admin client:** React web application
- **Backend:** Node.js + Express, REST API
- **Database:** PostgreSQL + Prisma
- **Authentication:** JWT in httpOnly cookie, bcrypt
- **Testing:** Jest, Supertest
- **Tools:** Docker Compose, GitHub, YouTrack, Figma

## Links

- **YouTrack project:** https://moldir-diploma.youtrack.cloud/projects/DIP
- **Documentation:** [`docs/`](docs/)
- **Diagrams:** [`docs/diagrams/`](docs/diagrams/)
- **Prototype:** [`prototype/`](prototype/)

## Repository structure

```
early-intervention-system/
├── README.md
├── docs/            # proposal, literature review, comparisons, requirements, test plan
│   └── diagrams/    # editable sources (.mmd) and PNG exports
├── prototype/       # mockups or link to the Figma prototype
├── src/             # application code (from the implementation stage)
├── tests/           # automated tests (from the implementation stage)
```

## Workflow

- Every work item is a YouTrack task with an ID like `DIP-5`.
- Branches: `DIP-5-requirements`.
- Commit messages: `DIP-5: Add functional requirements and acceptance criteria`.
- Changes are merged into `main` through Pull Requests that reference the YouTrack task.
- Each pre-defense submission is marked with a tag: `pre-defense-1`, `pre-defense-2`, `final-pre-defense`.
