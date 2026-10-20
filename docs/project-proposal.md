# Project proposal and scope

## Project
**Mobile Application for Tracking Physical Activity and User Health** (working product name: MoveWell)

## Team and supervision

| Member | Cohort | Proposed responsibility (confirm with the team) |
|---|---|---|
| Maratova Oryngul | SE-2426 | Literature review, user discovery, and requirements |
| Bekzhan Danelya | SE-2426 | Repository coordination, architecture, and technology comparison |
| Kazbek Aigerim | SE-2426 | UX prototype and verification/evaluation |

**Supervisor:** Kamila Tanyrbergenova (contact details are listed in the project README, as supplied by the team).

## Problem
People may have activity information spread across phone health platforms, fitness apps, and manual notes. Differences in device compatibility, missing or inaccurate measurements, unclear data sources, permission friction, and privacy concerns can make it hard to review personal trends. The project will test whether a simple activity log and history with transparent data provenance addresses a real user need.

## Provisional users and relevance
The initial audience is adults who use a smartphone and want to record everyday activity and review personal trends. This audience is provisional. The current relevance rationale is based on the literature review and the existing-app comparison; no user interviews or client agreement have yet been supplied. The proposed discovery plan is 3–5 short semi-structured conversations. See [`research/interview-summary.md`](research/interview-summary.md) for the protocol and results template.

## Aim
Design and implement a mobile app that supports recording physical activity and reviewing selected trends, with transparent data handling and measurable usability.

## Objectives
1. Critically review mobile activity tracking research and existing products.
2. Validate the target users' needs through user discussions or client evidence.
3. Define prioritized, verifiable functional and non-functional requirements.
4. Compare and justify the mobile framework, activity data source, and storage approach.
5. Prepare architecture diagrams and a clickable prototype.
6. Implement an MVP if feasible within the project schedule and team skills.
7. Verify core behavior and evaluate basic usability and data consistency without claiming clinical benefit.

## Expected outcomes
- A structured literature review and system/technology comparisons.
- A validated project scope and requirements with acceptance criteria.
- Editable architecture diagrams and screen prototype.
- If time permits, a runnable MVP with manual activity entry, goal, summary, and history.
- A documented verification/evaluation report.

## MVP scope
- Daily physical-activity summary with source labels.
- Manual entry for activity type, duration, and date.
- Personal goal and a seven-day history view.
- Optional reminder only if platform support and user validation allow it.
- Permission-denial fallback, privacy information, and data removal/export design.

## Out of scope for the first release
- Diagnosis, treatment, medical recommendations, or clinical decision support.
- Continuous GPS/location collection.
- Cloud account, social network, or public leaderboard.
- AI coaching or claims of improving health outcomes.
- Replacing a trainer or clinician.

## Constraints and assumptions
Platform and framework are not final. Health-data access depends on OS permissions and device support. User-research results are pending. Proposed team responsibilities require confirmation. The project checkpoint is 24 October 2026; the full application is not required at that checkpoint.

## Links
- [GitHub repository](https://github.com/danelyaab/Diploma_Project)
- [YouTrack MoveWell board](https://movewell.youtrack.cloud/agiles/204-1/current)
- [Clickable prototype](prototype/index.html)
- [Architecture source and exports](../diagrams/)
