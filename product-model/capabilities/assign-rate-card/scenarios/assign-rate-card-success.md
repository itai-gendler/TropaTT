---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Choose a card, reachable record or business target, priority and effective dates."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::rate-cards"
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "A Rate-card assignment is kept."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "rate-card-assignment"
        effect: "creates"
        facts:
          - "Target"
          - "Priority"
          - "Effective from"
          - "Effective to"
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

# Assign rate card: successful operation

## Trigger

Choose a card, reachable project or business target, priority and effective dates.

## Outcome

A Rate-card assignment is kept.
