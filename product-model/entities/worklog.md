---
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/worklog/WorklogController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/WorklogService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/EarningsService.php"
---

# Worklog

Owner/Task/context/date/minutes/intervals/note/activity/currency; rate snapshots/provenance/ambiguity/lock facts; Unlocked/Locked.

## Information kept

- **Owner** — Person whose time is recorded.
- **Task** — Referenced work.
- **Project** — Resolved work context.
- **Date** — Logging date.
- **Minutes** — Recorded duration.
- **Started at** — Optional interval start.
- **Ended at** — Optional interval finish.
- **Note** — Entry note.
- **Activity** — Activity classification.
- **Currency** — Snapshot currency.
- **Cost rate** — Cost snapshot.
- **Bill rate** — Billing snapshot.
- **Payout rate** — Payout snapshot.
- **Provenance** — Resolved source and ambiguity information.
- **Locked** — Entry lock designation.

## States

### Unlocked

The recorded time is available for ordinary editing.

### Locked

The recorded time carries a lock designation.
