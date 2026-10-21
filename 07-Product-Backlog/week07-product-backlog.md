# Product Backlog: RCHN Patient Intake and Scheduling System

**Consultant:** David Zupinski
**Role:** Associate Consultant, NovaTech Consulting
**Engagement:** RCHN
**Date:** October 20, 2026

## User Story Fundamentals

As a clinic intake coordinator, I want a clear result after saving an appointment, so that I know whether the patient is booked and can avoid duplicate booking attempts. The so-that clause explains the underlying value: confidence in the record and less checking and rework, rather than merely adding a confirmation screen.

## Ordered Product Backlog

Stories are ordered for the proposed phase-one horizon, not assigned to a Sprint. Acceptance criteria are proposed for stakeholder and Developer validation.

### Story 1 - Standardize intake

**User Story:** As a clinic intake coordinator, I want to record the agreed required intake information consistently at each RCHN clinic, so that patient registration is complete and staff can rely on the same information across six clinics.

**Acceptance Criteria:** Given any of the six clinics, when intake opens, then the same approved required fields are identified. Given missing required data, when save is attempted, then the missing fields are identified and no completed intake is recorded. Given valid data, when saved, then the information is retained and success is confirmed.

**Story Points:** 5
**MoSCoW Priority:** Must Have

### Story 2 - View appointment availability

**User Story:** As a clinic scheduling staff member, I want to view available appointment slots for a selected clinic and date, so that I can offer a patient an available time without checking separate schedules.

**Acceptance Criteria:** Given a selected clinic and date, when availability loads, then available slots show their time and clinic. Given no available slots, then an explicit no-availability message appears. Given a failed load, then an error is shown rather than presenting unavailable data as current.

**Story Points:** 5
**MoSCoW Priority:** Must Have

### Story 3 - Book with dependable confirmation

**User Story:** As a clinic intake coordinator, I want to book a selected slot for the confirmed patient and receive an unambiguous result, so that I know whether the appointment is recorded and can avoid duplicate bookings.

**Acceptance Criteria:** Given a confirmed patient and available slot, when booking succeeds, then one appointment is recorded and its patient, clinic and time are confirmed. Given simultaneous requests for the same slot, then only one booking succeeds and the other receives a conflict message. Given a failed save, then no success confirmation appears and staff can check status before retrying.

**Story Points:** 8
**MoSCoW Priority:** Must Have

### Story 4 - Carry forward entered information

**User Story:** As a medical assistant, I want to see previously saved intake information in the same patient workflow, so that I do not re-enter information already supplied during registration.

**Acceptance Criteria:** Given authorized access and saved intake data, when the same patient workflow is opened, then those saved values remain available. Given a different patient, then the previous patient data is not carried forward. Given an unauthorized role, then access is denied.

**Story Points:** 5
**MoSCoW Priority:** Should Have

### Story 5 - Explain incomplete intake

**User Story:** As a clinic intake coordinator, I want to see field-specific guidance for incomplete intake entries, so that I can correct omissions without restarting registration.

**Acceptance Criteria:** Given an incomplete required field, when validation occurs, then its label and corrective guidance are shown. Given other valid entries, then they remain present while the omission is corrected. Given corrected required fields, then the missing-field messages clear and valid intake can be saved.

**Story Points:** 3
**MoSCoW Priority:** Should Have

### Story 6 - Patient self-scheduling

**User Story:** As a RCHN patient, I want to book an available appointment through a patient-facing online portal, so that I can arrange a visit without contacting clinic scheduling staff.

**Acceptance Criteria:** Proposed for future refinement: Given an authenticated patient and an available slot, when a booking succeeds, then a confirmation identifies the clinic and time. Given a slot already taken, then booking is rejected and availability can be refreshed. Patient identity, access and portal scope require approval before implementation.

**Story Points:** 13
**MoSCoW Priority:** Won't Have This Time

## Estimation, Dependencies and INVEST Review

Points express relative effort, complexity and uncertainty, not hours. Story 5 is the 3-point baseline. Stories 1, 2 and 4 are 5 points because they add shared data, state or access handling. Story 3 is 8 points because concurrent requests and failed saves need additional testing. Story 6 is a provisional 13 and must be split before selection. Developers should re-estimate with implementation knowledge. Story 3 depends on availability and a confirmed patient record; Story 4 depends on saved intake; Story 5 refines Story 1 rather than duplicating its basic required-field checks. Identity rules, required fields and authorized roles must be clarified before Sprint selection.

INVEST: Each story has one user-valued capability and observable criteria. Stories are negotiable about implementation, and estimates provide a starting point for refinement. Independence is limited by the explicit dependencies above; Developers can use test fixtures while sequencing integrated delivery. Stories 1-5 are intended as Sprint-sized slices subject to team validation. The deferred portal is not ready and requires splitting. No story is considered Done solely because its acceptance criteria pass: the team Definition of Done also applies.

## Prioritization Rationale

### Must Have Justification

Stories 1-3 are Must Have for the proposed phase-one intake and scheduling replacement. Standardized required information addresses inconsistent workflows across six clinics; availability and reliable booking make scheduling usable. Story 3 directly addresses uncertain saves and double bookings in the Week 3 research. The order is 1, 2, 3, 4, 5, 6: establish consistent intake, expose availability, then complete reliable booking. Stories 4-5 reduce re-entry and correction effort; temporary manual review makes them Should Have. Must Have describes the planning horizon, not an automatic Sprint 1 commitment. The Product Owner owns ordering; Developers forecast Sprint work using capacity, dependencies and the Sprint Goal.

### Won't Have Rationale

Story 6, patient self-scheduling, is Won’t Have This Time. Week 5 presents a patient portal as a scope option, while the established replacement addresses staff intake and scheduling. I recommend deferring the portal to protect phase-one focus; it adds patient identity/access design and another workflow. Reconsider it after sponsor scope approval, validated patient needs, and assessment of cost, capacity and integration risks. Its 13-point estimate is provisional and signals further splitting/refinement, not a delivery promise.

## Backlog Reflection

### Persona Connection

Story 4 is supported by the Week 3 finding that medical assistants repeatedly enter patient information. My saved persona, Maya, also needs a connected workflow that preserves information and reduces unnecessary screens and rework. Carrying saved data into the same patient workflow addresses that need. Patient separation and authorization criteria make the proposal testable. No new interviews or measured improvements are claimed.

### Scope Connection

Story 2 develops the Week 5 appointment scheduling replacement scope option into a specific capability: select a clinic/date and view slots, with explicit empty and error states. These details let Developers discuss tests and relative effort without dictating implementation. The Week 5 GitHub folder currently contains only a placeholder, so I use the published Week 5 scenario rather than claim a verified prior scope decision. Phase-one inclusions and exclusions remain recommendations requiring sponsor confirmation.

## Sources

- [Week 7 assignment](https://jaguars.acm.org/courses/it-3310/week7/assignment.html)
- [Week 5 scope scenario](https://jaguars.acm.org/courses/it-3310/week5/assignment.html)
- [Saved Week 3 persona and vision](https://github.com/zupinskid/IT3310-ProjectPortfolio/blob/main/Product%20Vision/week03-product-vision.md)

*NovaTech Consulting | IT 3310 | Governors State University | Fall 2026*
