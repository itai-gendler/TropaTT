---
domain: "time-analytics"
singleton: true
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

# Finance settings

Singleton currency/markup/global range configuration and displayed auto-close configuration.

## Information kept

- **Currency** — Default currency.
- **Markup** — Fallback pricing markup.
- **Locked ranges** — Global locked-date range configuration.
- **Auto-close** — Displayed automatic closing configuration.
