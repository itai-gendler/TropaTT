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
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Time analytics

Recorded time, interval calculations, permitted financial calculations and period controls.
