---
appliesTo:
  - type: "capability"
    id: "browse-own-earnings"
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

# Own earnings group currencies without making payments

Own earnings selects the current Account and requested date range, groups currencies without converting them and is not a payment or an organization-isolation guarantee.
