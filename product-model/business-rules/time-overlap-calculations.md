---
appliesTo:
  - type: "capability"
    id: "browse-time-analytics"
    contexts:
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
---

# Time reports distinguish recorded unique and overlapping time

Time reports distinguish recorded minutes, the union of valid intervals and their overlapping intersections. A sum of durations does not substitute for unique working time, and invalid/missing intervals retain the implemented report treatment.
