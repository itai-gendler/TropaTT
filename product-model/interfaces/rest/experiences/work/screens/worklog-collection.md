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

# Worklog collection

Time-entry listing and creation with visible-person scope and response-specific financial filtering.
