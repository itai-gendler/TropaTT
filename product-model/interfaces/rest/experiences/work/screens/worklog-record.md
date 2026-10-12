---
entities:
  - entity: "worklog"
    shows:
      - "Owner"
      - "Task"
      - "Project"
      - "Date"
      - "Minutes"
      - "Started at"
      - "Ended at"
      - "Note"
      - "Activity"
      - "Currency"
      - "Cost rate"
      - "Bill rate"
      - "Payout rate"
      - "Provenance"
      - "Locked"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/app.php"
---

# Worklog record

Addressed recorded time, edits and deletion outcomes.
