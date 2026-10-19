# Project Proposal

## Project title

**Development of a Digital System for Managing Early Intervention Programs**

## Team and supervisor

| Name | Role |
|---|---|
| Yergesh Moldir Batyrbekkyzy | Student, individual project (analysis, design, implementation, testing, documentation) |
| Basheyeva Zh.O. | Supervisor, School of Software Engineering, Astana IT University |

## Problem statement

Early intervention is a set of services for young children with developmental delays or disabilities and for their families. Each child receives an individual program: goals, types of sessions (speech therapy, psychological support, physical therapy, etc.), their intensity and schedule.

To work effectively, specialists need to see the whole program of a child, know which sessions were planned and which were actually held, and track progress towards goals. In practice, this information is often kept in different places: paper journals, spreadsheets, messengers and personal notes. This leads to several problems:

- the full picture of a child's program is not available in one place;
- it is difficult to check whether planned sessions were held and how regular attendance is;
- the history of execution and feedback is lost or fragmented;
- administrators spend a lot of time manually preparing reports;
- coordination between several specialists working with the same child is complicated.

## Target users

| User | Needs |
|---|---|
| Early intervention specialist | Create and run individual programs, see the schedule, record held sessions, attendance and comments |
| Administrator of an early intervention centre | Manage specialists, the catalog of programs and session types, schedules; view reports |

Children and parents are not direct users of the prototype.

## Aim

To develop a working prototype of a web-based information system for structured planning, scheduling and tracking of individual early intervention programs.

## Objectives

1. Analyse the domain and existing solutions, collect requirements from potential users.
2. Compare technologies and select a stack justified by the requirements.
3. Specify functional and non-functional requirements with acceptance criteria.
4. Design the system architecture, data model and user interface.
5. Implement the core modules: roles and access, program catalog, individual plans, calendar, attendance and execution tracking, reports.
6. Test the key scenarios and evaluate the result against the baseline (manual tracking in spreadsheets).
7. Prepare documentation and a demonstration with test data.

## Expected outcomes

- A working web prototype with role-based access for specialists and administrators.
- Verifiable end-to-end scenario: **create a program → assign sessions to the calendar → record execution and attendance → generate a report**.
- Project documentation: requirements, architecture, diagrams, test plan and results.
- Demonstration data set (no real personal data).

## Project scope

**In scope:**
- authentication, user roles and access rights;
- catalog of programs and session types;
- individual intervention plans with goals;
- calendar scheduling of sessions;
- attendance tracking and execution history with comments;
- reports on program execution;
- functional testing of key scenarios.

**Out of scope:**
- processing real personal or medical data of children;
- integration with state medical information systems;
- billing and payments;
- native mobile applications;
- a portal for parents.

## Engineering complexity

The project is a full software system, not a static website. Its complexity comes from:

- **Data model:** related entities (users, roles, children, programs, goals, session types, plans, sessions, attendance, comments, reports) with integrity constraints.
- **Access control:** different rights for specialists and administrators; a specialist sees only assigned children.
- **Scheduling logic:** recurring sessions, time conflicts between specialists, rescheduling and cancellations.
- **Execution tracking:** comparison of planned and actually held sessions, calculation of attendance and execution rates.
- **Reporting:** aggregation of data by child, specialist and period.
- **Client-server architecture:** web client, REST API and relational database, with automated tests.
- **Data protection:** the system is designed for sensitive data, so security requirements are considered even though the prototype uses only test data.

## Key risks (initial)

| Risk | Mitigation |
|---|---|
| Limited access to real specialists for interviews | Contact several centres in advance; use online interviews |
| Scope too large for one student | Prioritise requirements (MoSCoW); implement "Must" first |
| Sensitivity of children's data | Use only demonstration data in the prototype |
