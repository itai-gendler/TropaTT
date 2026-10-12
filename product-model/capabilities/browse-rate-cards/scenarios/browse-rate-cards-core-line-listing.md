---
kind: "edge"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "List core price-list lines without a registered financial.field_policy entry."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::rate-cards"
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "Rate-card line cost, bill and payout fields remain in the scoped response. The optional filtering branch is not taken."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "rate-card-line"
        effect: "reads"
        facts:
          - "Person"
          - "Role"
          - "Activity"
          - "Cost rate"
          - "Bill rate"
          - "Payout rate"
          - "Currency"
          - "Effective from"
          - "Effective to"
          - "Note"
    contexts:
      web-work:
        place: "web::work::rate-cards"
      rest-work:
        place: "rest::work::rate-card-lines"
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

# Core line listing

## Trigger

List core price-list lines without a registered financial.field_policy entry.

## Outcome

Rate-card line cost, bill and payout fields remain in the scoped response. The optional filtering branch is not taken.
