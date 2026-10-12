---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Missing title or invalid card input is rejected."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::rate-cards"
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "Missing title or invalid card input is rejected."
    kind: "condition"
    actor: "root-administrator"
    entities: []
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

# Create rate card: refused or unavailable operation

## Trigger

Missing title or invalid card input is rejected.

## Outcome

Missing title or invalid card input is rejected.
