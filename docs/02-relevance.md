# Evidence of Relevance

## 1. Statistical data

| Fact | Source | Status |
|---|---|---|
| About 743.9 thousand people with disabilities lived in Kazakhstan in 2025; children under 18 made up 15.7% of them | Kazinform, citing the Ministry of Labour and Social Protection (inform.kz) | Verified (official data) |
| In 2025 there were about 114.7–117 thousand children with disabilities in Kazakhstan, and the number is growing | Lada.kz, citing the Ministry of Labour, 30.08.2026 | Verified (official data) |
| In 2025 about 10.9 thousand children with disabilities lived in Astana; children are almost 30% of all people with disabilities in the capital | Lada.kz, 30.08.2026 | Verified (official data) |
| Children with special needs may wait months for an examination before rehabilitation starts | Profile.ru, interview with officials | Partly verified (media source, older data) |
| About one in four children aged 2–4 in Kazakhstan does not develop according to age norms (MICS 2024); early intervention services remain largely inaccessible, especially under 3 | UNICEF Kazakhstan | Verified (international organisation) |
| Since June 2025 Development and Early Intervention Centres work at polyclinics; over 40 thousand children received help there | Ministry of Health of RK, via inbusiness.kz | Verified (official data) |

**Conclusion from the data:** the number of children who need developmental support in Kazakhstan is large (over 110 thousand children with an official disability alone, not counting children with developmental delays without a disability status) and is growing. Each such child needs an individual program with several specialists, which creates a large volume of planning and tracking work.

International sources for comparison (Eurostat, Statistics Denmark, U.S. NLM data sites, UNECA statistics) were recommended by the supervisor and will be used in the literature review for comparison with other countries.

## 2. Research methods

| Method | Participants | Goal | Status |
|---|---|---|---|
| Online survey for parents (main method) | 13 parents (Google Forms, 20–23.10.2026) | How parents get information about the program, schedule and progress; attitude to data sharing; questions in `02-survey.md` | Done (13 answers), still open |
| Short conversations | 3–5 parents | Deeper understanding of problems and needs | Planned before 24.10.2026 |
| Conversations with specialists | 1–2 specialists (if available) | Check how plans and attendance are kept (H1, H4); guide in `02-interview-guide.md` | Planned, optional |
| Consultation with supervisor | Basheyeva Zh.O. | Confirm scope, roles and key functions | 23.10.2026 |

## 3. Hypotheses and their status after the survey

| ID | Hypothesis | Related requirements | Status |
|---|---|---|---|
| H1 | Specialists keep plans and attendance in paper journals, Excel or messengers, not in a dedicated system | Whole project | Partly confirmed (indirectly: 62% of parents get the schedule through messengers, only 1 of 13 through a centre app). Must be checked with specialists |
| H2 | Parents do not have one place where they can see the child's plan, schedule and progress | FR-21, FR-23, FR-25 | Confirmed: only 38% have such a place; 62% have it partly or not at all |
| H3 | When a child moves to a new specialist, the parent has to repeat the child's history and bring documents again | FR-05, FR-09 | Confirmed: 9 of 10 parents who changed specialists had to do it every time or sometimes |
| H4 | Preparing reports on held sessions takes specialists significant time | FR-26 | Not checked yet (specialists' side) |
| H5 | Parents want to control who sees the child's data | FR-09, FR-11, NFR-03 | Mostly confirmed: 7 of 13 chose the maximum importance (5 of 5), 4 chose 3, 2 chose 2. For some parents this is less important, so access control must be simple and not slow down the work |
| H6 | Parents prefer a phone to a computer | Technology decision 1 (Flutter app for parents) | Confirmed: 92% (12 of 13) prefer a phone |

## 4. Survey results

**Sample:** 13 parents, Google Forms, 20–23 October 2026, distributed through the author's personal network (friends, relatives and their acquaintances).

| Question | Result |
|---|---|
| Child's age | 3–5 years: 46% (6); older than 7: 38% (5); 5–7: 15% (2); under 3: 0 |
| Specialists the child works with (several answers) | Speech therapist: 77% (10); psychologist: 23% (3); special educator (defectologist): 23% (3); physical therapist: 8% (1); other / on their own / none: 4 answers |
| Number of specialists at the same time | One: 46% (6); two: 38% (5); three: 15% (2). **54% work with two or more specialists** |
| How parents learn the schedule | WhatsApp / Telegram: 62% (8); paper schedule: 15% (2); orally: 15% (2); centre app: 8% (1) |
| Recommendations and progress information from the specialist | Always: 62% (8); **only if the parent asks: 31% (4)**; sometimes: 8% (1) |
| One place where all sessions, plan and progress are visible | Yes: 38% (5); partly: 46% (6); no: 15% (2) |
| Repeating the child's history and bringing documents to a new specialist | Every time: 46% (6); sometimes: 23% (3); no: 8% (1); did not change specialists: 23% (3) |
| Importance of deciding which specialist sees the child's data (1–5) | 5 (maximum): 54% (7); 3: 31% (4); 2: 15% (2) |
| Would use an app / website with the child's profile, schedule and recommendations | Yes: 54% (7); rather yes: 38% (5); rather no: 8% (1); no: 0. **92% positive** |
| Preferred device | Phone: 92% (12); computer: 8% (1); tablet: 0 |

**Open question "What would be most useful in such a system?"** (13 answers, grouped):
- Recommendations from the specialist and tracking the child's progress (5 answers).
- Schedule of sessions and all information in one place (4 answers).
- Safe storage of the child's data and quick access to it (2 answers).
- Not carrying all the papers when moving to a new specialist, and being able to report a cancellation in the app (1 answer, directly matching H3 and FR-20).
- Feedback, mobility, convenience (3 answers).

**Main findings:**
1. The problem of scattered information is real: most parents get the schedule through messengers, and 62% do not have one place for the plan, schedule and progress.
2. Moving to a new specialist means repeating the child's history for almost every parent who has done it. This supports the parent-owned child profile.
3. For almost a third of parents, recommendations and progress come only when they ask. This supports comments and home recommendations after every session (FR-23).
4. Interest in the system is high (92% would rather use it), and parents clearly prefer a phone, which confirms the Flutter app for parents.
5. Parents' priorities in the open answers match the core functions: recommendations, progress, schedule, all data in one place.

**Limitations:**
- Small convenience sample (13 people from the author's network); results show tendencies, not statistically representative data.
- 38% of the children are older than 7, i.e. older than the typical early intervention age (0–6). Their parents still describe the same problems with specialists, but results for younger children may differ.
- The specialists' side (H1, H4) is not covered by the survey.
- The survey is still open; the results will be updated.

## 5. Conversations

Planned: short conversations (about 10 minutes) with 3–5 parents, and if possible with 1–2 specialists, using the guide in `02-interview-guide.md`. **Not conducted yet**; planned before 24.10.2026. Results will be added as one short table per conversation.
