---
appliesTo:
  - type: "capability"
    id: "preview-rates"
  - type: "capability"
    id: "log-time"
  - type: "capability"
    id: "recalculate-worklog-rates"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/rate/RateCardController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/rate/RateController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/RateResolutionService.php"
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

# Rate families resolve independently with filtered trace

Rate resolution handles cost, bill and payout independently across Task overrides, matching assignments/default cards and user fallback. It retains specificity, effective dates, priority, ambiguous candidates, currency handling and the implemented cost-derived markup/payout fallback. Trace and candidate output receive actual family/configuration filtering. Scoped row access does not turn every settings or fallback lookup into a workspace-specific record.
