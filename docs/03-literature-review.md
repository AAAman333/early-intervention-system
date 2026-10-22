# Literature Review

## 1. Purpose and method

**Purpose:** to find out what is already known about (a) the need for early intervention and its organisation, (b) digital tools for developmental screening and for supporting families, (c) coordination of information between parents and specialists, (d) patient- / parent-controlled sharing of health data, and (e) search and recommendation of specialists - and to decide which approaches and limitations the project should take into account.

**Search:** PubMed Central, JMIR journals, Frontiers, ACM Digital Library, SAGE, Google Scholar, national sources of Kazakhstan (Ministry of Health, UNICEF Kazakhstan, Nazarbayev University repository).
**Keywords:** early intervention; developmental surveillance / screening; mHealth; telehealth; caregiver coaching; care coordination; children with special health care needs; personal health record; patient-controlled consent; doctor recommender system; Kazakhstan.
**Inclusion criteria:** peer-reviewed articles and official reports, mainly 2021–2026; older works kept only when they are foundational (marked *F*). Sources must be directly related to one of the themes above.

**Result:** 17 sources: 14 peer-reviewed scientific publications , 1 master's thesis and 2 official sources.

## 2. Thematic review

### 2.1 The need for early intervention, especially in Kazakhstan

According to UNICEF Kazakhstan, about one in four children aged 2–4 does not develop according to age norms (MICS 2024), and early childhood intervention services remain largely inaccessible, especially for children under three [S16]. The state has started to respond: since June 2025 Development and Early Intervention Centres have been opened at polyclinics, where a child's development is assessed, a plan is formed and a multidisciplinary team works with the child [S17]. A Kazakhstani literature review stresses that early intervention programmes are costly, need inter-agency collaboration and work best with active participation of parents [S14]. A qualitative study with parents of children with autism in Kazakhstan showed that families face many barriers when trying to access early intervention, and rely on personal networks and persistence to find services [S15].

**Takeaway for the project:** the demand is large and growing, services are being built right now, and parents have difficulty finding and navigating them. A tool that helps parents notice a problem early and reach a suitable specialist addresses a real gap. **Limitation:** the Kazakh sources are mostly official reports and one small qualitative study (5 parents); the project's own survey (`02-relevance.md`) is needed to confirm the problem locally.

### 2.2 Developmental surveillance and digital screening

The CDC "Learn the Signs. Act Early." milestone checklists were revised in 2022 by an expert group: the new checklists include milestones that at least 75% of children reach by a given age and are designed to discourage a "wait-and-see" approach [S1]. Systematic reviews show that many screening and surveillance tools exist, that parent-completed tools are acceptable to families, and that web-based surveillance can support early detection, but follow-up after a positive screen is often weak [S2, S3]. A pilot study turned a validated screening tool into a text-message format; parents found it usable, which shows that validated questionnaires can be moved to mobile channels [S4].

**Takeaway:** a parent-completed milestone checklist in the mobile app is an evidence-based, realistic "smart" feature. **Limitations the project accepts:** (1) the app must use an existing validated / evidence-informed list (CDC milestones) rather than invented questions; (2) the result is a *recommendation to consult a specialist*, not a diagnosis; (3) the screening is only useful if it leads to action — therefore the result is connected to the search for a specialist (2.6). Clinical validation of the app is out of scope.

### 2.3 Digital delivery and the role of parents

A 2025 systematic review found that early intervention delivered via telehealth, mostly as videoconference coaching of caregivers, achieved outcomes comparable to traditional formats [S5]. Providers and caregivers in the US Part C system saw telehealth as feasible, but also reported challenges with engagement and technology [S6]. A review of 20 years of virtual coaching studies confirms that technology is increasingly used to support families, but notes gaps in reporting how it is implemented [S7].

**Takeaway:** parents are active participants in early intervention, so they need access to the plan, schedule and home recommendations (FR-21, FR-23). **Limitation:** video sessions are not included in the project scope; the system supports coordination around face-to-face sessions.

### 2.4 Coordination of information between families and specialists

Studies with caregivers of children with special health care needs describe a large emotional and logistical burden caused by fragmented services [S12]. When there is no designated coordinator, parents themselves collect and pass health information between providers, and professional care coordination is the exception rather than the norm [S13].

**Takeaway:** this directly supports the core design decision: **one child profile owned by the parent**, which is shared with each new specialist instead of repeating the history (FR-05, FR-09, FR-13, FR-25). **Limitation:** these studies are from the US healthcare context; the situation in Kazakhstan is checked by the survey (hypothesis H3).

### 2.5 Parent- / patient-controlled data sharing

Research on personal health records proposes platforms where the patient grants and withdraws access to their records with fine-grained consent and access logs [S8]. A 2026 mixed-methods study (16 health system leaders, 523 patients) found that patients see transparency and granular control as protection against risks, while leaders see them in terms of ethics and informed consent [S9].

**Takeaway:** the project's consent model (request → accept → revoke, with an access log; FR-09 – FR-12, NFR-03) follows established principles. A simpler centralised implementation is chosen instead of blockchain, because the prototype does not need decentralised trust. **Limitation:** legal requirements of Kazakhstan on personal and medical data are not analysed in depth; the prototype uses only demo data (NFR-04).

### 2.6 Search, rating and recommendation of specialists

Online healthcare platforms provide a lot of information about doctors, but patients find it hard to choose; a hybrid recommender that combines multi-criteria ratings, reputation and doctor profile information improved recommendation accuracy [S10]. A study from China built a multi-dimensional index for evaluating doctors on online platforms, showing that a single star rating is not enough to describe service quality [S11].

**Takeaway:** the planned "smart search" ranks verified specialists in the parent's city by specialisation match, rating and nearest free time. Ratings use several criteria (e.g. communication, results, punctuality) rather than one number. **Limitation:** collaborative filtering needs a lot of rating data, which a new system does not have; therefore the project uses a transparent weighted score instead of a machine-learning recommender.

## 3. Analysis table

| ID | Source | Year | Type | Approach | Main findings | Limitations | Use in project |
|---|---|---|---|---|---|---|---|
| S1 | Zubler J.M. et al., *Evidence-Informed Milestones for Developmental Surveillance Tools*, Pediatrics 149(3) | 2022 | Peer-reviewed, expert review | Expert group, 11 criteria, literature normative data | Revised CDC milestones reached by ≥75% of children; discourages wait-and-see | US norms; surveillance, not a diagnostic tool | Content of the screening checklist |
| S2 | *The Acceptability and Effectiveness of Web-Based Developmental Surveillance Programs: Rapid Review*, JMIR | 2020 *F* | Peer-reviewed, rapid review | Review of web-based surveillance for 0–6 y | Web-based surveillance is acceptable and can support early detection | Few high-quality studies | Justifies digital screening |
| S3 | *Developmental screening tools for identification of children with developmental difficulties in high-income countries: a systematic review*, Frontiers | 2025 | Peer-reviewed, systematic review (PRISMA) | Psychometrics, acceptability, follow-up | Many tools; parents accept them; referral / follow-up often missing | High-income countries only | Link screening to specialist search |
| S4 | *Usability and Acceptability of a Text Message-Based Developmental Screening Tool for Young Children: Pilot Study*, JMIR Pediatrics and Parenting | 2019 *F* | Peer-reviewed, pilot | Validated PEDS:DM questions sent by SMS | Parents found mobile screening usable | Small pilot, low-income US mothers | Mobile format of screening |
| S5 | *Early Intervention for Children With Developmental Disabilities and Their Families via Telehealth: Systematic Review*, JMIR | 2025 | Peer-reviewed, systematic review | Effectiveness and implementation of telehealth EI | Mostly videoconference caregiver coaching; outcomes comparable | Heterogeneous studies | Parents as active participants |
| S6 | *Telehealth Delivery in Part C Early Intervention: Provider and Caregiver Perspectives*, PMC | 2022 | Peer-reviewed, survey study | Perspectives of providers and caregivers | Telehealth feasible; engagement and technology challenges | US Part C context | Usability requirements for parents |
| S7 | *Twenty Years of Virtual Coaching: A Systematic Review of Single-Case Studies…*, J. of Special Education Technology | 2026 | Peer-reviewed, systematic review | 13 single-case studies, SCARF | Technology increasingly supports families | Single-case designs, children 2–5 | Context for digital support of families |
| S8 | *A blockchain-enabled sharing platform for personal health records*, PMC | 2023 | Peer-reviewed, design + prototype | Patient-controlled consent, access control model | Granular consent, patient can stop sharing | Blockchain adds complexity | Consent model (FR-09 – FR-12) |
| S9 | *Health System Leaders' and Patients' Perspectives on a Patient-Controlled Data-Sharing Platform*, Proc. ACM HCI (CSCW), DOI 10.1145/3788079 | 2026 | Peer-reviewed, mixed methods | Prototype, 16 interviews, 523-patient survey | Patients value transparency and granular control | Research data sharing, adults | Access log, revoke (NFR-03) |
| S10 | Shambour Q.Y. et al., *A doctor recommender system based on collaborative and content filtering*, IJECE | 2022 | Peer-reviewed, algorithm + experiment | Hybrid multi-criteria collaborative + content filtering | Better accuracy under data sparsity | Needs rating data | Weighted ranking of specialists |
| S11 | Liu S., Zhang Y., *Designing a doctor evaluation index system for an online medical platform…*, Frontiers in Public Health | 2023 | Peer-reviewed, Delphi study | IS success model, multi-dimensional index | One rating is not enough; several dimensions needed | Chinese platforms | Multi-criteria rating of specialists |
| S12 | *Issues navigating the healthcare delivery system among caregivers of children and youth with special healthcare needs: a qualitative study*, PMC | 2026 | Peer-reviewed, qualitative | Focus groups, 22 caregivers | Large burden from fragmented systems | One US state | Shared child profile |
| S13 | *Parent Perspective on Care Coordination Services for Their Child with Medical Complexity*, Children | 2017 *F* | Peer-reviewed, qualitative | Parent interviews | Parents act as coordinators and carry information between providers | Medically complex children | Shared profile and history (FR-25) |
| S14 | *Development of the nervous system at an early age and subsequent intervention*, Science & Healthcare (Semey) 26(5) | 2024 | Peer-reviewed, literature review (Kazakhstan) | Review of early intervention approaches | Programmes need parents' participation and state / inter-agency support | Narrative review | Local context |
| S15 | Begaliyeva A., *Parental perspectives of barriers and facilitators to accessing early intervention services for children with ASD*, Nazarbayev University | 2024 | Master's thesis, qualitative | In-depth interviews with 5 parents in Kazakhstan | Many barriers; parents rely on networks and persistence | 5 participants, ASD only | Local evidence of access problems |
| S16 | UNICEF Kazakhstan, Early childhood development / ECI programme materials | 2024–2026 | Official | MICS 2024 data | ~1 in 4 children aged 2–4 off-track; ECI largely inaccessible | Secondary data | Relevance, scale |
| S17 | Ministry of Health of RK via inbusiness.kz, Development and Early Intervention Centres | 2025–2026 | Official / news | — | Centres at polyclinics since June 2025; assessment → plan → team | News source | Process the system supports |

## 4. Synthesis

**What is known.** Early detection and early intervention are effective, and parents play a central role. Validated milestone checklists exist and can be completed by parents on mobile devices. Families of children with special needs suffer from fragmented information and often coordinate care themselves. Patient-controlled, consent-based data sharing is an accepted approach. Patients need help choosing a provider, and multi-criteria ratings describe providers better than a single score.

**Gap the project addresses.** The reviewed works treat these topics separately: screening tools do not lead the parent to a specialist; care-coordination studies describe the problem but not a tool for families in Kazakhstan; consent platforms target adult patients and research. The project combines them in one chain for the local context: **screening → finding a suitable verified specialist in the parent's city → sharing the child profile with consent → plan, sessions and progress visible to both sides.**

**Limitations the project takes into account.**
- Screening is informational, based on CDC evidence-informed milestones; it is not a diagnosis and is not clinically validated in this project.
- Ranking of specialists is a transparent weighted score, not ML, because there is no rating data at the start.
- No video sessions and no integration with state systems.
- Local evidence is limited; it is complemented by the project survey.
- Only demonstration data is used; legal analysis of medical data handling in Kazakhstan is a topic for future work.

## 5. References

- S1 — https://veipd.vcu.edu/media/veipd/pdfsarchives/evidence-informed-milestones-for-developmental-surveillance-tools.pdf (Pediatrics 2022;149(3):e2021052138)
- S2 — https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7206511/
- S3 — https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11732054/
- S4 — https://pediatrics.jmir.org/2019/1/e10814
- S5 — https://jmir.org/2025/1/e66442/PDF
- S6 — https://pmc.ncbi.nlm.nih.gov/articles/PMC9510265/
- S7 — https://journals.sagepub.com/doi/10.1177/01626434261456276
- S8 — https://pmc.ncbi.nlm.nih.gov/articles/PMC10366433
- S9 — https://api.crossref.org/works/10.1145%2F3788079 (preprint: https://arxiv.org/pdf/2603.26010)
- S10 — https://ijece.iaescore.com/index.php/IJECE/article/view/27808
- S11 — https://www.frontiersin.org/journals/public-health/articles/10.3389/fpubh.2023.1185036/epub
- S12 — https://www.ncbi.nlm.nih.gov/pmc/articles/PMC13488566/
- S13 — https://pmc.ncbi.nlm.nih.gov/articles/PMC5483620
- S14 — https://newjournal.ssmu.kz/upload/iblock/0c9/xcw1zzw0gzdmpks3mgsrsoeat5vhcgkr/160_176_5_26_2024.pdf
- S15 — https://nur.nu.edu.kz/items/f4f8949b-2c96-4391-bc90-44f77b919e4b/full
- S16 — https://untalent.org/jobs/re-advertisement-national-expert-to-support-ecd-programmes-with-unicef-in-kazakhstan ; https://www.unicef.org/kazakhstan/en/ensuring-best-start-every-child-kazakhstan-0
- S17 — https://inbusiness.kz/ru/last/kazahstan-razvivaet-set-centrov-podderzhki-razvitiya-detej ; https://inbusiness.kz/ru/last/centry-rannego-razvitiya-i-vmeshatelstva-izmenyat-podhod-k-detskoj-medicine-v-rk
