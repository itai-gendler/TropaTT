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
  - entity: "finance-settings"
    shows:
      - "Locked ranges"
      - "Auto-close"
  - entity: "rate-locked-period"
    shows:
      - "From"
      - "To"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/app.php"
---

# Time reports

Time overlap projections, own earnings and scoped row/global period controls.
