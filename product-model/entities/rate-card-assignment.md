---
domain: "rate-cards"
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

# Rate-card assignment

Card, Project/Counterparty target, priority and effective dates.

## Information kept

- **Target** — Project or counterparty address.
- **Priority** — Resolution priority.
- **Effective from** — First effective date.
- **Effective to** — Last effective date.
