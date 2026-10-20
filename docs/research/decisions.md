# Project Decisions

This draft records the current proposal, interview evidence, and project decisions.

## Team responsibilities

- **Date:** 20 October 2026
- **Supervisor:** Kamila Tanyrbergenova

| Work area | Proposed owner | Confirmation |
|---|---|---|
| Literature review, user discovery, and requirements | Maratova Oryngul | Approved |
| Repository coordination, architecture, and technology comparison | Bekzhan Danelya | Approved |
| UX prototype and verification/evaluation | Kazbek Aigerim | Approved |

Each member should confirm or request a change. Record the final allocation and supervisor's comments in the approval table below. Each student should contribute using an individual Git account, and significant changes should be reviewed through a pull request.

## User research evidence

- **Status:** Three exploratory interviews completed; findings remain preliminary
- **Date and format:** 20 October 2026, in person
- **Participants:** P01–P03, anonymized
- **Source:** `docs/research/interview-summary.md`
- **Consent to publish anonymized notes:** Not confirmed. Do not publish the detailed notes publicly until participant consent is confirmed or access is restricted appropriately.
- **Sample limitation:** Three interviews meet the minimum of three discussions, provided the participants meet the intended eligibility criteria. Confirm that they are adults and smartphone users before claiming that the target audience has been validated. One or two more interviews may broaden the evidence but are not required to meet the minimum.

### Findings and design implications

| Finding from these interviews | What it supports | Limitation / response |
|---|---|---|
| All three participants expressed interest in manually adding activity. | Include manual entry for activity type, date/time, and duration in the MVP. | This is a small exploratory sample, not a population estimate. |
| All three wanted to see activity records, summaries, or statistics over a period. | Provide a daily summary and activity history; start with a manageable seven-day view. | One participant requested multi-year statistics; defer longer history until scope and implementation time are confirmed. |
| At least two participants explicitly described personal activity goals or progress toward a goal. | Let users set and edit their own activity goal and show progress. | Do not prescribe weight-loss or medically appropriate goals. |
| Reminder preferences differed: one wanted an evening reminder, one wanted context-aware reminders on inactive days, and one rarely uses reminders. | If included, reminders should be optional and configurable. | Do not enable reminders by default or assume all users want them. |
| Preferences about data sharing differed. One participant preferred limiting sharing to activity heart rate; another was open to several health measures and location; another was generally relaxed but did not want to provide identity documents. | Explain data sources and permissions; request only data needed for a user-selected feature. | The interviews do not establish a general privacy concern or justify collecting health/location data. Keep health measures and location out of the MVP unless separately justified and approved. |

The interviews do **not** justify weight-loss or muscle-gain prescriptions, menstrual-cycle-based activity recommendations, clinical interpretation, or collection of broad health data. Treat these as out of scope for the initial release.

## Decision 1: Target users

- **Status:** Proposed — interview eligibility and supervisor confirmation pending
- **Date:** 20 October 2026
- **Current proposal:** Adults who use a smartphone and want to record everyday physical activity and review personal activity trends.
- **Evidence:** Three in-person interviews were conducted on 20 October 2026. Participants described current use of activity apps or interest in tracking and manual logging. The notes do not explicitly record participant ages or eligibility checks.
- **Decision:** Keep the audience provisional until the team confirms that all three participants were adults and smartphone users. Refine the segment if the interviews indicate a narrower group.
- **Limitations and risks:** The sample is small and exploratory; it cannot establish population-wide needs.
- **Follow-up:** Confirm eligibility without adding identifying details to public notes; update the proposal and requirements from the findings.

## Decision 2: MVP platform and application framework

- **Status:** Proposed — team skills, target devices, and supervisor confirmation pending
- **Date:** 20 October 2026
- **Options considered:** Flutter; React Native; native development (Swift for iOS and Kotlin for Android).
- **Provisional direction in the README:** Flutter.
- **Reason for provisional direction:** A shared codebase may reduce implementation effort and help maintain a consistent interface within the project schedule.
- **Limitations and risks:** Health-platform integrations may require native plugins. The team has not confirmed Dart skills, target operating systems, or the exact health-data API needed. If only one operating system is targeted or native API access is essential, native development may be more suitable.
- **Decision:** No platform or framework is approved yet. Compare options against team skills, required APIs, device availability, and schedule before committing.
- **Follow-up:** Confirm target operating system(s), review team experience, and make a small proof of concept for required activity-data access.

## Decision 3: Activity data source

- **Status:** Proposed — platform and permissions need confirmation
- **Date:** 20 October 2026
- **Options considered:** Manual activity entry; integration with the phone's health platform; direct phone sensors or continuous GPS; wearable integration.
- **Provisional direction in the README:** Manual entry as the reliable baseline; consider the operating system's health platform only where available and justified. Exclude continuous GPS from the MVP.
- **Interview evidence:** All three participants expressed interest in manual activity entry. The interviews show differing preferences about health data and location; they do not establish a need for automatic health-data or GPS integration.
- **Reason:** Manual entry is supported by the current interviews and avoids making the MVP dependent on a particular device or permission. A health-platform connection could be considered after the target platform and requirements are confirmed.
- **Limitations and risks:** Manual logging may take more effort. Available APIs and permissions differ between iOS and Android; users can deny or revoke access, and imported values may be incomplete.
- **Decision:** No platform integration is approved yet. Keep manual logging in the MVP and decide on health-platform integration after a technical proof of concept and supervisor review.
- **Follow-up:** Confirm the target platform; if integration remains in scope, review HealthKit or Health Connect requirements and test granted, denied, and revoked permission states.

## Decision 4: Data storage

- **Status:** Proposed — confirm after team and supervisor review
- **Date:** 20 October 2026
- **Options considered:** Local database (for example, SQLite/Drift); Firebase Firestore; PostgreSQL with a REST API.
- **Provisional direction in the README:** Local-first storage for the MVP, with an export and deletion design; no cloud synchronization in the initial version.
- **Reason:** A local-first design avoids requiring a server and may reduce collection of personal data. It fits manual activity logging and history.
- **Limitations and risks:** Local storage does not provide multi-device synchronization or cloud backup. The specific database, data-retention behavior, and protection of local records remain undecided.
- **Decision:** No storage technology is approved yet; compare the alternatives and confirm that local storage satisfies the requirements.
- **Follow-up:** Record the selected database, export format, retention, and deletion behavior in the architecture and requirements documents.

## Decision 5: Application structure and component communication

- **Status:** Proposed
- **Date:** 20 October 2026
- **Options considered:** Modular in-process services; REST API; GraphQL API.
- **Provisional direction in the README:** Modular in-process services, with repository interfaces around storage and health-data access.
- **Reason:** The proposed local-first MVP does not need a remote API. Separating UI and data-access responsibilities keeps the initial implementation manageable.
- **Limitations and risks:** Cloud synchronization or a separate backend would require revisiting the architecture.
- **Decision:** Use this as the draft architecture unless user research or the selected platform creates a justified need for a backend.
- **Follow-up:** Reflect the selected boundaries in the component diagram and revise it after platform and storage decisions are made.

## Proposed MVP scope

- **Status:** Proposed
- **Date:** 20 October 2026

### Include in the initial version

- Daily physical-activity summary with a clear source label.
- Manual entry for activity type, date/time, and duration.
- A user-defined activity goal and a seven-day history view.
- Permission-denial fallback if a health-platform integration is later selected.
- Clear privacy information and a design for user data removal/export.
- Optional, configurable reminders only if platform support and further user validation allow them.

### Keep out of scope for the first release

- Diagnosis, treatment, medical recommendations, or clinical decision support.
- Weight-loss or muscle-gain prescriptions, cycle-based recommendations, and clinical interpretation of health measures.
- Continuous GPS/location collection.
- Cloud accounts, social networks, and public leaderboards.
- AI coaching or claims that the app improves health outcomes.
- Wearable hardware development.

- **Evidence:** Manual logging, summaries/history, and goals are supported by the three exploratory interviews; reminder preferences vary. The interviews do not establish a need for health metrics, location, or medical recommendations.
- **Limitations and risks:** The scope may still be too broad for the schedule. Prioritize manual activity logging, goals, and history before optional reminders or integrations.
- **Follow-up:** Confirm the MVP after the team validates interview eligibility and reviews the scope with the supervisor.

