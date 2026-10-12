---
entities:
  - entity: "worklog"
    shows:
      - "Owner"
      - "Task"
      - "Project"
      - "Date"
      - "Minutes"
      - "Currency"
      - "Payout rate"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# My earnings

Own payout calculations grouped by currency over the requested dates.
