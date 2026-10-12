---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply supported person/record/activity selectors, rates and effective dates."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::rate-cards"
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "A Rate-card line is saved under the resolved card."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "rate-card-line"
        effect: "creates"
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

# Add rate-card line: successful operation

## Trigger

Supply supported person/role/activity selectors, rates and effective dates.

## Outcome

A Rate-card line is saved under the resolved card.
