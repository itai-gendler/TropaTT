---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Supply supported selector and rate changes."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "Rate-card line selector, financial or effective-date facts change."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "rate-card-line"
        effect: "changes"
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

# Edit rate-card line: successful operation

## Trigger

Supply supported selector and rate changes.

## Outcome

Rate-card line selector, financial or effective-date facts change.
