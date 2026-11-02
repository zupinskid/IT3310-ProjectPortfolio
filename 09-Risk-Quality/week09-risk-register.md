# Risk Register: RCHN Patient Intake and Scheduling System

**Consultant:** David Zupinski  
**Role:** Associate Consultant, Project Manager, NovaTech Consulting  
**Engagement:** Riverside Community Health Network (RCHN)  
**Date:** November 2, 2026

## Bring Forward

### Week 5 source gap and proposed assumptions
The Week 5 Project Plan Foundation folder contains only .gitkeep. No completed Week 5 assumptions were available. A1-A3 below are proposed assumptions for this analysis, not quotations from prior work or approved commitments. The requirement to cite my own documented Week 5 assumptions remains unmet. The connections are disclosed rather than represented as completed prior work.

- A1 - Data validation before cutover (proposed): Existing appointment records can be mapped, reconciled and approved before each clinic uses the replacement system.
- A2 - Protected training capacity (proposed): Clinic managers can release designated staff across all six clinics and shifts for training and competency checks before their rollout wave.
- A3 - Parallel specialist capacity (proposed, carried forward from Week 8): Separate qualified specialists are available for intake configuration and clinic/date availability work, allowing activities B and C to run in parallel.

### Week 7 backlog item
Week 7 Story 3 - Book with dependable confirmation (Must Have, 8 points): As a clinic intake coordinator, I want to book a selected slot for the confirmed patient and receive an unambiguous result, so that I know whether the appointment is recorded and can avoid duplicate bookings. Criteria require one booking under concurrent requests, the correct patient/clinic/time, and no success confirmation after a failed save. Story 4 also requires authorized access and separation between patient workflows.

### Week 8 schedule item
Week 8 activity D - Integrate booking and verify conflict/error handling: 10 working days, Finish-to-Start after B and C, proposed start Week 4. The four-activity A-B-D path takes 25 working days; C has five days of float. The proposed pilot-acceptance milestone is at the end of Week 6. These are estimates requiring approval, not actual dates or reported progress.

## Risk Entries

### Risk 1 - Inaccurate data reaches live scheduling
**Category:** Technical  
**Description:** If unresolved migration mapping or reconciliation defects carry incorrect patient, clinic or appointment-time data into production, then RCHN may create missed or duplicate bookings and fail dependable-booking acceptance requirements.  
**Assumption / artifact link:** A1 - Data validation before cutover (proposed; Week 5 source unavailable). Week 7 Story 3 and the Week 8 pilot-acceptance milestone provide downstream traceability.  
**Probability:** Medium  
**Impact:** High  
**Score:** 6 (High)  
**Rating justification:** Medium probability: the Week 9 lecture scenario reports appointment discrepancies, but their scope and remediation effectiveness are unknown. High impact: incorrect production data can invalidate Story 3, disrupt six-clinic scheduling and force rollback or delay. The current discrepancy is an issue; recurrence or escape into production is the future threat.  
**Response Strategy:** Mitigate. Profile and reconcile source-to-target appointment records, correct mapping rules, and rehearse migration. Require critical booking tests and documented reconciliation before each release. Test restoration and rollback. If the gate fails, hold the affected rollout wave, log the issue and reforecast remediation with RCHN acceptance representatives.  
**Trigger or Monitoring Condition:** Any unreconciled patient/clinic/time mismatch or failed critical booking test at a migration rehearsal or release-readiness checkpoint. Review discrepancies after every trial load.  
**Owner:** Developer. The Developer can inspect mapping logic, reconcile test results and coordinate defect repair with RCHN IT. The Project Manager controls escalation and clinic representatives validate workflow accuracy.  
**Status:** Open

### Risk 2 - Training gaps cause rollout workflow failures
**Category:** Stakeholder  
**Description:** If designated staff cannot complete training and demonstrate intake and booking tasks before their clinic's rollout wave, then inconsistent workarounds and user errors may reduce service quality and prevent operational readiness.  
**Assumption / artifact link:** A2 - Protected training capacity (proposed; Week 5 source unavailable). Links to Week 8 package 3.1, training and readiness at six clinics.  
**Probability:** Medium  
**Impact:** High  
**Score:** 6 (High)  
**Rating justification:** Medium probability: the Week 9 scenario identifies incomplete training at two clinics, while remaining time and coverage are unverified. High impact: inability to operate core intake and booking can block clinic acceptance and disrupt service. Incomplete training is a current issue; future workflow failure or failed rollout readiness is the uncertain consequence.  
**Response Strategy:** Mitigate. Agree protected training time and shift coverage with clinic managers, track readiness by clinic and role, and offer targeted makeup sessions. Assess booking, rescheduling and intake correction through demonstrations. If readiness is not achieved, arrange supervised support and seek approval to defer the affected wave rather than declare attendance sufficient.  
**Trigger or Monitoring Condition:** Required staff lack a confirmed training slot at the readiness planning checkpoint, miss a required session without a makeup plan, or fail an agreed workflow demonstration before release.  
**Owner:** Project Manager. The Project Manager can coordinate the training schedule, clinic coverage, readiness dependencies and escalation. Clinic managers release staff and trainers assess competence.  
**Status:** Open

### Risk 3 - Incorrect access configuration exposes patient data
**Category:** Compliance  
**Description:** If role permissions or patient-context separation are configured incorrectly in the new intake workflow, then staff may view another patient's information or access data beyond their approved role, undermining privacy and acceptance.  
**Assumption / artifact link:** Week 7 Story 4 requires denied access for unauthorized roles and no carry-forward between different patients. Week 8 activity A must confirm identity and access rules.  
**Probability:** Low  
**Impact:** High  
**Score:** 3 (Medium)  
**Rating justification:** Low probability is provisional because reviewed artifacts report no confirmed access-control failure; absence of a report is not proof of safety. High impact reflects potential privacy exposure and failed acceptance. Its score of 3 does not justify postponing inexpensive pre-UAT negative testing.  
**Response Strategy:** Mitigate. Agree a role/access matrix with RCHN IT and its privacy representative. Use synthetic test data to test denied access, patient switching and session boundaries before UAT. Review permissions and retest after changes. Treat any unauthorized exposure as an issue, contain it under RCHN procedures and stop the affected release pending clearance.  
**Trigger or Monitoring Condition:** Any test grants access to an unauthorized role, carries data into another patient's workflow, or lacks an approved permission rule before UAT.  
**Owner:** Developer. The Developer implements access rules and can run negative tests and repair defects. RCHN IT and its designated privacy representative validate approved roles and escalation requirements.  
**Status:** Open

### Risk 4 - Shared staffing prevents planned parallel work
**Category:** Resource  
**Description:** If the same specialist is assigned to both Week 8 activities B and C or is unavailable when needed, then the planned parallel configuration work may become sequential and delay activity D or require costly replacement capacity.  
**Assumption / artifact link:** A3 - Parallel specialist capacity (proposed, explicitly assumed in Week 8). B has zero float and C has five days in the four-activity network.  
**Probability:** Medium  
**Impact:** Medium  
**Score:** 4 (Medium)  
**Rating justification:** Medium probability: Week 8 assumes separate specialists but does not confirm assignments. Medium impact: resequencing, backups or C's float may contain a limited gap, but delays to B or a longer shortage can move D and the pilot. Reassess impact upward when the forecast exceeds available float.  
**Response Strategy:** Mitigate. Review named capacity with the team before Sprint planning, confirm coverage for B and C, and identify a qualified backup. Sequence independent work within confirmed capacity and monitor C's five-day float. If availability fails, reforecast D and escalate approved staffing or scope tradeoffs without shortening critical tests.  
**Trigger or Monitoring Condition:** A specialist is double-booked or unassigned at Sprint planning, B is forecast to slip, or C is forecast to consume its five working days of float before D.  
**Owner:** Scrum Master. The Scrum Master can surface capacity impediments and facilitate realistic planning with Developers. The Project Manager resolves cross-project assignments and approval of extra staffing costs.  
**Status:** Open

### Risk 5 - Deferred portal expands phase-one scope
**Category:** Schedule  
**Description:** If stakeholders add the deferred patient self-scheduling portal to phase one without approved funding and capacity, then additional identity, interface and testing work may displace core staff-booking requirements and extend the rollout schedule.  
**Assumption / artifact link:** Week 7 Story 6 is Won't Have This Time, with a provisional 13-point estimate needing refinement. The Week 8 schedule excludes the portal pending sponsor confirmation.  
**Probability:** Medium  
**Impact:** Medium  
**Score:** 4 (Medium)  
**Rating justification:** Medium probability: a portal is a known scope option, but no added request is confirmed. Medium impact: its new identity and interface work could displace core features, while formal scope control can contain exposure. Avoidance depends on an approved exclusion; until then the scope baseline remains an open decision.  
**Response Strategy:** Avoid. Seek sponsor confirmation of a phase-one baseline excluding the portal and retain Story 6 for a later approved horizon. Route portal requests through change review before work begins. If an authorized change includes it, revise scope, estimates, acceptance tests and dates and assess the resulting new risks; do not silently absorb the work.  
**Trigger or Monitoring Condition:** A request or Sprint proposal includes Story 6 before an approved change, or a stakeholder treats patient self-scheduling as a phase-one commitment. Review during backlog refinement.  
**Owner:** Product Manager. The Product Manager can explain product outcomes and scope tradeoffs with stakeholders and the Product Owner. The Project Manager and sponsor approve delivery-baseline changes within their authority.  
**Status:** Open

## Assumption Connection
Risk 1 is linked to proposed A1: the uncertain ability to reconcile and approve data before cutover threatens dependable booking quality and the pilot-acceptance milestone. Risk 2 is linked to proposed A2: uncertain staff release time and shift coverage threaten six-clinic training completion, service quality and rollout readiness. Risk 4 is linked to proposed A3: uncertain separate specialist availability threatens the planned B/C concurrency and D's start. A3 is traceable to my Week 8 assumptions. These links explain the planning logic but cannot satisfy the missing requirement for my own documented Week 5 assumptions.

## Score Justification
Course qualitative scale: Low=1, Medium=2, High=3. Score=probability x impact. Priority bands: Low 1-2, Medium 3-4, High 6-9. Ratings are judgment-based planning estimates, not measured failure rates. Reassess with technical and clinic leads after response evidence is available. All triggers and acceptance gates below are proposed for agreement.

Risk 1 and Risk 2 tie for the highest course score (6). Their separate probability and impact reasons appear in the entries above. Risk 3 has a lower score but requires privacy tests before UAT because consequence and timing matter alongside numeric priority.

## Risk Reflection

### Highest Priority Risk and Project Impact
Risk 1 deserves the most attention, even though Risk 2 has the same score of 6. Data defects may be shared across clinics, so a small rollout alone does not ensure containment. Quality and readiness: incorrect patient, clinic or time data violates dependable-booking criteria and should block the affected release. Schedule: reconciliation and retesting may extend activity D or the pilot-acceptance gate and delay later waves. Cost and resources: migration repairs, extra test cycles and support consume Developer and clinic time, potentially requiring approved additional capacity. Stakeholder confidence: unreliable appointments can reduce staff trust and increase checking and workarounds. Prioritize evidence of reconciliation and critical-test completion, then reassess residual exposure. Sponsor decisions on timing should preserve agreed quality gates rather than assume that a numeric score authorizes accepting defective data.

### Risk vs. Issue Distinction
I checked the wording of all five entries against the available Week 7 backlog, Week 8 schedule and saved Week 9 lecture activity. This is an artifact review, not a claim that I inspected live systems or interviewed clinic staff. Risk 1 concerns future production escape, whereas the lecture's existing appointment discrepancies require issue management now. Risk 2 concerns future operational failure or failed readiness, whereas the reported incomplete training is already an issue. For Risk 3, the reviewed artifacts contain requirements and unconfirmed access decisions, but no confirmed unauthorized disclosure. For Risk 4, the schedule explicitly assumes specialist availability and reports no actual missed assignment or delayed B/C activity. For Risk 5, the backlog defers the portal and no approved phase-one expansion is evidenced. Unknown status does not prove an event has not occurred, so owners should validate each entry at the next review. A confirmed defect, missed required readiness gate, actual capacity conflict or unauthorized scope start belongs in the issue log with an owner and resolution date. Preserve the original risk history, execute or adapt the response and monitor residual threats. This distinction prevents monitoring a current problem while corrective work goes unassigned.

## Portfolio Artifacts
- [Completed Excel Risk Register](Week09-Risk-Register-David-Zupinski.xlsx)
- Matching analysis PDF submitted separately to Blackboard.
- Week 5 source gap remains disclosed; no prior approval or undocumented work is claimed.

## Sources
- [Week 9 assignment](https://jaguars.acm.org/courses/it-3310/week9/assignment.html)
- [Week 9 lecture](https://jaguars.acm.org/courses/it-3310/week9/lecture.html)
- [My Week 7 backlog](https://github.com/zupinskid/IT3310-ProjectPortfolio/blob/main/07-Product-Backlog/week07-product-backlog.md)
- [My Week 8 schedule](https://github.com/zupinskid/IT3310-ProjectPortfolio/blob/main/08-Project-Schedule/week08-project-schedule.md)
- [Week 5 folder checked; only placeholder present](https://github.com/zupinskid/IT3310-ProjectPortfolio/tree/main/05-Project-Plan-Foundation)
- Course Resources: IT3310_Week9_RiskRegister_Template(1).xlsx (three-sheet structure and formulas preserved).
- Saved Week 9 Risk Identifier and Assessor lecture activity (October 28, 2026): current discrepancies and incomplete training distinguished from future threats.

*NovaTech Consulting | IT 3310 | Governors State University | Fall 2026*
