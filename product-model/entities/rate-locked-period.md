---
domain: "time-analytics"
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
---

# Rate-locked period

Kept exact from/to range; not regenerated grouped lock summaries.

## Information kept

- **From** — Exact first locked date.
- **To** — Exact last locked date.
