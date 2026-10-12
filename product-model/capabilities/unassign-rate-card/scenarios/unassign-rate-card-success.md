---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select an existing card-target assignment."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::rate-cards"
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "The Rate-card assignment is removed."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "rate-card-assignment"
        effect: "removes"
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

# Unassign rate card: successful operation

## Trigger

Select an existing card-target assignment.

## Outcome

The Rate-card assignment is removed.
