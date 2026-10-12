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

# Rate-card line

Card/person/Role/activity selectors, rates/currency/effective dates/note.

## Information kept

- **Person** — Optional person selector.
- **Role** — Optional role selector.
- **Activity** — Optional activity selector.
- **Cost rate** — Cost selector value.
- **Bill rate** — Billing selector value.
- **Payout rate** — Payout selector value.
- **Currency** — Line currency.
- **Effective from** — First effective date.
- **Effective to** — Last effective date.
- **Note** — Line note.
