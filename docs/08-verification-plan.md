# Verification and Evaluation Plan
## 1. What is checked and how

| Level | What | How | Tools | When |
|---|---|---|---|---|
| Unit tests | Core business logic: overlap check (FR-19), recurrence (FR-18), attendance rate (FR-26), access check (FR-12), screening scoring (FR-32), search ranking (FR-34) | Automated, 20–30 tests | Jest | Stage 2–3, with each module |
| Mobile widget tests | 3–5 key parent screens (login, child profile, request) | Automated | flutter_test | Stage 2–3 |
| API tests | Main endpoints return correct data and refuse access without rights (NFR-02) | Automated, ~15 tests | Jest + Supertest | Stage 2–3 |
| Manual functional tests | Every "Must" requirement by its acceptance criterion | Test case table (section 2) | Browser, Android emulator / phone, Google Sheet with results | Before each pre-defense |
| Security / access checks | A specialist without access, a parent of another child, a non-logged user cannot see data | Manual + API tests | Browser, mobile app, Postman | Stage 2–3 |
| Performance | Main screens ≤ 2 s with demo data (NFR-06) | Seed script with 100 children, 15 specialists, 5,000 sessions; measure in browser DevTools and Flutter DevTools | Chrome DevTools, Flutter DevTools | Final stage |
| Usability | Real users can complete key tasks | Test with 3–5 people (section 4) | Stopwatch, short questionnaire | Final stage |
| Comparison with baseline | System vs current way (Excel/paper/messenger) | Experiment (section 5) | Stopwatch | Final stage |

## 2. Manual test cases (key examples)


| ID | Requirement | Steps | Expected result |
|---|---|---|---|
| TC-01 | FR-01 | Register a parent with valid email and password, log in | Login succeeds, parent dashboard opens |
| TC-02 | FR-01 | Log in with a wrong password | Error message, no access |
| TC-03 | FR-03 | Register a specialist, try to accept a request before verification | Action is not available |
| TC-04 | FR-05 | Parent creates a child profile | Profile is shown in the parent's account |
| TC-05 | FR-09, FR-10 | Parent sends a request, specialist accepts it | Child appears in the specialist's list |
| TC-06 | FR-12 | Specialist B opens the child's URL without access | "Access denied" (403) |
| TC-07 | FR-11 | Parent revokes access | Specialist no longer sees the child; history is kept |
| TC-08 | FR-14, FR-15 | Specialist creates an active plan with 2 goals | Plan visible to the specialist and the parent |
| TC-09 | FR-18 | Schedule 2 sessions per week for 4 weeks | 8 sessions in the calendar |
| TC-10 | FR-19 | Create a session overlapping an existing one | Warning, session not saved |
| TC-11 | FR-22, FR-23 | Mark a session as held with a comment | Status and comment visible to the parent |
| TC-12 | FR-26 | Report for 4 weeks: 6 held, 1 missed, 1 cancelled | Planned 8, held 6, attendance 75% |
| TC-13 | FR-31, FR-32 | Parent of a 3-year-old completes the screening, answering "not yet" to 3 speech questions | Result shows "worth discussing" for speech, recommends a speech therapist, shows the "not a diagnosis" note |
| TC-14 | FR-33 | Search for speech therapists in Astana | Only verified speech therapists from Astana are shown |
| TC-15 | FR-34 | Three test specialists with known rating and free slots | Order of results matches the score calculated by hand |
| TC-16 | FR-35 | Parent without held sessions tries to rate a specialist | Rating is not available; after a held session it becomes available |

## 3. Metrics

| Metric | Target | How measured |
|---|---|---|
| "Must" requirements passed | 100% by the final pre-defense | Manual test results |
| Automated tests passing | 100% | `npm test` |
| Test coverage of core modules | ≥ 60% (NFR-09) | Jest coverage report |
| Page load time with demo data | ≤ 2 s (NFR-06) | Chrome DevTools |
| Task success rate in usability test | ≥ 80% of tasks completed without help | Observation |
| Time to record a held session | ≤ 30 s, ≤ 3 clicks (NFR-07) | Stopwatch |
| User satisfaction | Average ≥ 4 of 5 | Short questionnaire after the test |

## 4. Usability test

- **Participants:** 3–5 people (specialists or parents from the survey; if not available, students acting as users, which will be noted as a limitation).
- **Tasks:** (1) parent: complete the development screening, find a speech therapist in Astana and send a request; (2) specialist: create a plan and schedule sessions for 2 weeks; (3) specialist: mark a session as held with a comment; parent: find this comment.
- **Measured:** completion (yes / with help / no), time, errors, 3 questions after the test (ease, clarity, would use: 1–5).
- **Conditions:** the same laptop, demo data prepared in advance, no instructions except the task text.

## 5. Comparison with the baseline

**Baseline:** the current way of work, assumed (to be confirmed by the survey, H1) to be paper journals / Excel tables plus messengers.

**Experiment:** the same participant performs two tasks in both ways, in alternating order:
1. Record 5 held sessions with short comments.
2. Prepare a monthly summary for one child: how many sessions were planned and held, attendance in %.

For the baseline, a prepared Excel template with the same data is used. Measured: time and number of errors (wrong numbers in the summary).

**Success criterion:** the system is at least as fast for task 1 and noticeably faster (at least 2 times) for task 2, with no errors in the report. The result will be presented in a table and chart at the final pre-defense.

## 6. Test environment

- Local deployment with Docker Compose (Node.js, PostgreSQL).
- Web application: Chrome and Safari on a laptop.
- Parent app: Android emulator and one real Android or iOS phone.
- Demonstration data only (NFR-04), generated by a seed script.
- Every test run is linked to a Git tag, so results can be reproduced.
