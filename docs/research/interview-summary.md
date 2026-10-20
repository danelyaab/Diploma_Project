# User research summary

## Status and handling

Three exploratory interviews were conducted in person on 20 October 2026. The team has not confirmed participants' consent to publish detailed transcripts. To avoid publishing participant-level material without that confirmation, this public file contains only aggregate findings; it does not include verbatim answers or individual interview records. Findings are preliminary and are not representative of all potential users.

The available notes do not document eligibility checks for age or smartphone use. Confirm those checks with the research team without adding identifying details. Detailed transcripts should be kept outside the public repository unless participants explicitly consent to publication. Earlier public commits may still contain the prior transcript version; removing the file content from the current branch does not erase it from Git history.

## Interview method and guide

The conversations were semi-structured and held in person. The guide covered current activity tracking, activity history, missing or inaccurate readings, manual entry, reminders, data-sharing preferences, and desired information on the home screen. Names and contact details are not recorded here.

## Aggregate results

| Evidence | Summary across three participants | Design implication |
|---|---|---|
| Current tracking context | One participant was not using an activity-tracking app; two used phone-based fitness or health apps | Support both first-time users and people supplementing existing tracking |
| Manual entry | All three expressed interest in adding activities manually or correcting incomplete records | Keep manual activity entry and editing in the MVP; label each record's source |
| Summary and history | All three wanted a clear way to review activity; two described daily goals or progress, while another emphasized longer-term statistics | Show a daily summary, user-defined goal progress, and at least seven days of history |
| Activity types | Participants mentioned activities beyond automatically counted steps; specific examples varied | Support manual logs for different activity types without promising automatic measurement of each |
| Reminders | Preferences varied: some wanted reminders in suitable contexts, while one rarely uses them | Make reminders optional, configurable, and easy to disable |
| Data sharing | Willingness to connect health or location data varied; participants expressed limits on personal information | Minimize data collection; keep integrations optional and explain permissions |

These findings are a small exploratory sample, not population estimates. Requests for medical or weight-loss guidance, additional health metrics, cycle-related features, and longer-term visualizations were not established as shared requirements. The MVP should allow users to set their own goals and display progress without prescribing medically appropriate targets.

## Traceability

- Requirements informed: FR-02, FR-03, FR-04, FR-05, FR-06, NFR-01, and NFR-07.
- Project proposal: [`../project-proposal.md`](../project-proposal.md).
- Project decisions: [`decisions.md`](decisions.md).
- Interview consent and eligibility must be confirmed before detailed participant-level findings are published.
