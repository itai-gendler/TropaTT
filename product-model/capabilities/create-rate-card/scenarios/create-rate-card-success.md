---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a title, currency and supported default designation."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::rate-cards"
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "An active Rate card is created within the resolved workspace."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "rate-card"
        effect: "creates"
        facts:
          - "Title"
          - "Description"
          - "Currency"
          - "Default"
          - "Archived at"
          - "Created at"
        to: "Active"
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

# Create rate card: successful operation

## Trigger

Supply a title, currency and supported default designation.

## Outcome

An active Rate card is created within the resolved workspace.
