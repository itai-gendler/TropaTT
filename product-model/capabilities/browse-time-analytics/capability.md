---
availability:
  - place: "web::work"
  - place: "rest::work"
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
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/security/FinancialFieldPolicy.php"
domain: "time-analytics"
---

# Browse time analytics

Worklog-based recorded, unique and overlapping time calculations are returned with permitted financial calculations.
