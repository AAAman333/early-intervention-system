# Project Management, Risks and Supervisor Feedback

## 1. Tools

| Tool | Purpose | Link |
|---|---|---|
| GitHub | Code and documents, branches and Pull Requests per task, tags per pre-defense | https://github.com/AAAman333/early-intervention-system |
| YouTrack | Tasks with responsible person, acceptance criteria, priority and deadline | https://moldir-diploma.youtrack.cloud/projects/DIP |

**Workflow:** YouTrack task (DIP-N) → branch `DIP-N-short-name` → commits `DIP-N: ...` → Pull Request with task ID → merge into `main` → link to PR added to the task → task closed when acceptance criteria are met.

## 2. Responsibilities

Individual project: all work is done by **Yergesh Moldir Batyrbekkyzy** (analysis, design, implementation, testing, documentation). The supervisor **Basheyeva Zh.O.** reviews key deliverables at checkpoints.

## 3. Milestones

| # | Milestone | Main deliverables | Target |
|---|---|---|---|
| M1 | Pre-defense 1 | Proposal, relevance, literature review, comparisons, requirements, architecture, mockups, verification plan (tag `prob-period-1` / `pre-defense-1`) | 24.10.2026 |
| M2 | Project skeleton | Repository structure (`server/`, `web/`, `mobile/`), Docker Compose, database schema (Prisma), empty Flutter and React apps connected to the API | +3 weeks after M1 |
| M3 | Core part 1 | Accounts and roles, specialist verification, child profiles, requests and consent-based access (FR-01 – FR-13) | Before pre-defense 2 |
| M4 | Pre-defense 2 | Working part 1 + plans and catalog (FR-14 – FR-16), tests for implemented modules (tag `pre-defense-2`) | Per university schedule |
| M5 | Core part 2 | Scheduling, attendance, progress, reports (FR-17 – FR-27) | After pre-defense 2 |
| M6 | Testing and evaluation | Manual test cases, usability test, baseline comparison, fixes | Before final pre-defense |
| M7 | Final pre-defense | Full prototype, documentation, demo (tag `final-pre-defense`) | Per university schedule |

## 4. Risks

| ID | Risk | Probability | Impact | Mitigation |
|---|---|---|---|---|
| R1 | Not enough real users for surveys and interviews | Medium | High | Online surveys in parent and specialist communities; ask the supervisor for contacts; start early |
| R2 | Scope too large for one developer | High | High | MoSCoW priorities; "Must" first; "Could" only if time remains |
| R3 | Sensitivity of children's data | Medium | High | Only demo data in the prototype; consent-based access; passwords hashed; no secrets in Git |
| R4 | Supervisor feedback changes requirements late | Medium | Medium | Regular short consultations; requirements versioned in Git |
| R5 | Scheduling logic (recurrence, conflicts) is more complex than expected | Medium | Medium | Implement simple weekly recurrence first; cover with unit tests |
| R6 | Learning new tools (Prisma, Docker) takes time | Low | Medium | Use tools close to existing experience (JavaScript, React, Node.js) |
| R7 | Loss of work | Low | High | Everything in GitHub; small frequent commits |
| R8 | Illness / exam period reduces available time | Medium | Medium | Buffer time before each pre-defense |
| R9 | Two clients (Flutter + React) double the interface work | High | Medium | All logic only on the server; the parent app covers only parent functions; shared API contract; parent screens first in Figma |

## 5. Dependencies

- Survey and interview results (DIP-3) → may change requirements priorities (DIP-7).
- Supervisor confirmation of roles and platform → technology choice (DIP-6) and mockups (DIP-9).
- Requirements (DIP-7) → architecture (DIP-8), verification plan (DIP-10).
- Architecture and data model → implementation tasks of stage 2.
