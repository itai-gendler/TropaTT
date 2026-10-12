---
domain: "time-analytics"
singleton: true
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

# Work settings

Singleton inspected worklog-policy configuration; configuration lifecycle unmapped.

## Information kept

- **Time policy** — Configured worklog eligibility, duration, dates and target-person controls.
