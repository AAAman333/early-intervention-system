# Development of a Digital System for Managing Early Intervention Programs

Diploma project, Astana IT University, School of Software Engineering.

A web-based information system that helps early intervention centres plan, schedule and track individual intervention programs for children: program goals, session types and intensity, calendar, attendance, execution history and reports.

## Problem statement

Early intervention programs are planned individually for each child: goals, types of sessions, intensity, attendance, execution and feedback. In practice this information is often kept in scattered paper records, spreadsheets and messengers. As a result, it is difficult for specialists to see the full picture of a child's program, to check whether planned sessions were actually held, and for administrators to prepare reports.

## Target users

- **Early intervention specialists** (psychologists, speech therapists, physical therapists, etc.) — create and run individual programs, record sessions and attendance.
- **Administrators of early intervention centres** — manage specialists, the program catalog and schedules, view reports.

The prototype uses demonstration data only. Real personal data of children is not collected or stored.

## Aim and expected outcomes

**Aim:** to develop a working prototype of an information system for structured planning and tracking of individual early intervention programs.

**Expected outcomes:**
- a working web prototype with role-based access;
- verifiable scenarios: creating a program → assigning sessions → recording execution → generating a report;
- project documentation (requirements, architecture, test plan) and demonstration data.

## Project scope

**In scope:**
- user roles and access rights (specialist, administrator);
- catalog of programs and session types;
- individual intervention plans;
- calendar scheduling of sessions;
- attendance tracking and execution history;
- reports on program progress;
- functional testing of the key scenarios.

**Out of scope:**
- processing of real personal or medical data of children;
- integration with state medical information systems;
- billing and payments;
- native mobile applications.

## Team and supervisor

| Name | Role | Responsibilities |
|---|---|---|
| Yergesh Moldir Batyrbekkyzy | Student (individual project) | Analysis, requirements, design, implementation, testing, documentation |
| Basheyeva Zh.O. | Supervisor | Weekly review of progress and key deliverables |

## Current status

**Stage: analysis and design (pre-defense 1).**

The topic and scope are approved by the supervisor. Current work: project proposal, evidence of relevance, literature review, comparison of existing systems and technologies, requirements, architecture diagrams, UI prototype and verification plan. No runnable code yet.

## Technologies

The final technology stack will be selected based on the technology comparison (see [`docs/`](docs/)). Planned components:
- web client (frontend);
- server-side REST API (backend);
- relational database;
- Git + GitHub for version control, YouTrack for task tracking.

## Links

- **YouTrack project:** https://moldir-diploma.youtrack.cloud/projects/DIP
- **Documentation:** [`docs/`](docs/)
- **Diagrams:** [`diagrams/`](diagrams/)
- **Prototype:** [`prototype/`](prototype/)

## Repository structure

```
early-intervention-system/
├── README.md
├── docs/            # proposal, literature review, comparisons, requirements, test plan
├── diagrams/        # editable sources (.drawio) and exports (.png)
├── prototype/       # mockups or link to the Figma prototype
├── src/             # application code (from the implementation stage)
├── tests/           # automated tests (from the implementation stage)
└── .gitignore
```

## Workflow

- Every work item is a YouTrack task with an ID like `DIP-5`.
- Branches: `DIP-5-requirements`.
- Commit messages: `DIP-5: Add functional requirements and acceptance criteria`.
- Changes are merged into `main` through Pull Requests that reference the YouTrack task.
- Each pre-defense submission is marked with a tag: `pre-defense-1`, `pre-defense-2`, `final-pre-defense`.

## Setup and run

Not available yet. Setup, run and test instructions will be added when runnable code appears.
