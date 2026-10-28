# Project Schedule: RCHN Patient Intake and Scheduling System

**Consultant:** David Zupinski  
**Role:** Associate Consultant, Project Manager, NovaTech Consulting  
**Engagement:** Regional Care Health Network (RCHN)  
**Date:** October 27, 2026

## Work Breakdown Structure

### 1.0 Planning and scope baseline
- 1.1 Shared intake, identity and access requirements
- 1.2 Technical constraints and acceptance plan
- 1.3 Sponsor-reviewed scope and delivery baseline

### 2.0 Intake and scheduling solution
- 2.1 Standardized intake with retained data and correction guidance
- 2.2 Clinic/date availability with empty and error states
- 2.3 Reliable booking, integration and acceptance evidence

### 3.0 Clinic readiness and rollout
- 3.1 Training materials and trained staff at all six clinics
- 3.2 Pilot deployment and observation evidence
- 3.3 Remaining-clinic rollout and operational verification

### 4.0 Post-launch support and handoff
- 4.1 90-day post-rollout support and issue resolution
- 4.2 Operating guides and support ownership transfer
- 4.3 Lessons learned and sponsor closure record

### WBS Rationale
The Week 5 portfolio folder contains no completed plan, so this WBS uses the published Week 5 scope options and my saved Week 7 backlog as a recommended baseline, not a verified sponsor approval. Group 2 covers standardized intake and scheduling across six clinics. Package 2.1 combines Stories 1, 4 and 5 because saved data and correction guidance refine one intake workflow; 2.2 covers Story 2, and 2.3 covers Story 3 plus integration and acceptance testing. Group 3 covers staff training and rollout at all six locations, and Group 4 covers the proposed 90-day support period and handoff. Group 1 captures the planning, access decisions and approvals needed to deliver these outcomes. Patient self-scheduling remains deferred as in Story 6. Billing integration, an executive dashboard and a separate mobile app are excluded recommendations requiring sponsor confirmation. Data migration extent, technical interfaces, staff availability and final acceptance authority still need clarification before baselining.

## Task Dependencies
- Confirm shared intake, identity and access requirements (A) -> Configure intake and retained-data workflow (B): Finish-to-Start.
- Configure intake and retained-data workflow (B) -> Integrate booking and verify conflict/error handling (D): Finish-to-Start.
- Configure clinic/date availability (C) -> Integrate booking and verify conflict/error handling (D): Finish-to-Start.

### Dependency Logic
The B-to-D Finish-to-Start relationship materially affects delivery because integrated booking needs a working patient/intake workflow. In my four-activity schedule, A-B-D takes 25 working days, while A-C-D takes 20. B has zero total float and C has five working days of float. A two-week (10-working-day) delay to B moves D from Week 4 to Week 6 and its completion from the end of Week 5 to the end of Week 7. Without mitigation, the expanded workbook's UAT acceptance milestone moves from Week 6 to Week 8, and the all-clinic rollout milestone from Week 13 to Week 15, with support and final handoff also two weeks later. C's float cannot absorb a delay on B's branch. The team can investigate additional qualified capacity, split verified integration components or move independent training preparation earlier, but must validate capacity and rework risks. It should not shorten acceptance testing or the promised support period simply to retain the original finish date.

## Activity Schedule
| ID | Activity | Duration (working days) | Predecessors | Start week |
|---|---|---:|---|---:|
| A | Confirm shared intake, identity and access rules | 5 | None | 1 |
| B | Configure intake and retained-data workflow | 10 | A | 2 |
| C | Configure clinic/date availability | 5 | A | 2 |
| D | Integrate booking and verify conflict/error handling | 10 | B,C | 4 |

### Scheduling Assumptions
These are preliminary estimates, not approved dates or a conversion of story points to days. I allow five working days for cross-clinic rules and access decisions, ten for intake validation/retained data, five for availability, and ten for booking integration and failure/concurrency tests. Five working days form a project week, with no holidays or planned gaps. A establishes common rules before B and C. Separate available specialists allow B and C to run in parallel; D waits for both usable outputs. A runs on days 1-5, B on 6-15, C on 6-10 and D on 16-25. Therefore the earliest start weeks are 1, 2, 2 and 4. This subset ends in Week 5 and is not the complete rollout schedule. Unconfirmed data/interface complexity or shared staffing could lengthen durations or prevent parallel work. The expanded workbook adds UAT, training, a proposed five-week pilot observation window, rollout and 13 weeks covering at least 90 calendar days of support. Confirm actual dates, staffing and scope before approval.

## Milestones

### 1. Core intake and scheduling accepted for pilot
**Target:** End of project Week 6 (proposed)  
**Duration:** 0  
**Exit criteria:** RCHN's designated acceptance representatives sign the UAT record. Tests demonstrate the same required intake fields at all six clinics, retained data only for the correct authorized patient workflow, clinic/date availability with empty/error states, a single successful booking under concurrent requests, and truthful failure/confirmation messages. No unresolved release-blocking defects remain. These acceptance thresholds and sign-off authority require confirmation.

### 2. All six clinics live and operationally verified
**Target:** End of project Week 13 (proposed)  
**Duration:** 0  
**Exit criteria:** The pilot observation review is approved, training completion is recorded for designated users at all six clinics, and each clinic passes an end-to-end intake-to-booking smoke test. RCHN signs the rollout checklist with support contacts, rollback arrangements and issue escalation ownership documented. This is a zero-duration rollout completion event; the separate 90-day support period follows.

### Critical Path Analysis
For the supplied independent exercise, A-B-D = 3 + 4 + 2 = 9 working days, and A-C-D = 3 + 6 + 2 = 11 working days. A-C-D is the critical path and the earliest project completion is 11 days. D must wait for both branches, so B has two days of total float; A, C and D have zero float under the stated assumptions. A two-day delay on a critical activity increases completion to 13 days unless an approved adjustment offsets it. This calculation is separate from my proposed RCHN schedule: its durations are A=5, B=10, C=5 and D=10, giving a 25-day A-B-D critical path and five days of float on C. Neither four-activity network represents the full deployment and support schedule.

## Schedule Reflection
### Scope Connection
Grouping 3, Clinic readiness and rollout, traces to the Week 5 scenario option for staff training at all six locations and the six-clinic replacement context. Package 3.1 supplies role-appropriate training materials and evidence of staff readiness. Package 3.2 establishes the pilot and observation evidence before wider deployment, while 3.3 verifies the remaining-clinic rollout. Training and rollout are necessary project work even though they are not individual Week 7 product stories. Pilot duration and rollout sequence are new scheduling assumptions. Because a completed Week 5 plan was not located, these are recommended inclusions requiring confirmation, rather than a claim about an approved earlier scope.

### Objective Connection
The all-six-clinics-live milestone marks a major delivery transition from implementation to post-launch support. It supports the scenario's authorized intake and scheduling replacement and the Week 7 goal of consistent staff workflows. I cannot verify a prior Week 5 SMART objective or claim a measured performance improvement. Week 13, training coverage, acceptance thresholds and the pilot observation period are proposed targets requiring sponsor and clinic-lead approval. Before baselining, confirm the earlier objectives, resources, calendar, operational readiness criteria and who signs acceptance. Any approved objective for reduced errors or processing time also needs a baseline and measurement method before this milestone can be treated as proof of that benefit.

## Expanded Excel Schedule
The accompanying workbook expands the four-activity subset into a proposed 26-week delivery and support timeline. Its activity codes extend the WBS package codes. Dates are estimates requiring scope and capacity approval. Milestones occur at the end of the indicated week. Five weeks of pilot observation reserve at least 30 calendar days; 13 post-rollout weeks reserve 91 calendar days for the proposed 90-day support commitment. Confirm actual calendar dates before approval.

## Sources
- [Week 8 assignment](https://jaguars.acm.org/courses/it-3310/week8/assignment.html)
- [Week 5 scope scenario](https://jaguars.acm.org/courses/it-3310/week5/assignment.html)
- [My Week 7 backlog](https://github.com/zupinskid/IT3310-ProjectPortfolio/blob/main/07-Product-Backlog/week07-product-backlog.md)
- Course Resources: IT3310_Week8_ProjectSchedule_Template.xlsx

*NovaTech Consulting | IT 3310 | Governors State University | Fall 2026*
