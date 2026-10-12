---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply supported price-list metadata."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::rate-cards"
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "Rate card metadata changes."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "rate-card"
        effect: "changes"
        facts:
          - "Title"
          - "Description"
          - "Currency"
          - "Default"
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

# Edit rate card: successful operation

## Trigger

Supply supported price-list metadata.

## Outcome

Rate card metadata changes.
