---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Create a price list as the new scoped default while another default exists."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::rate-cards"
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "A Rate card is created as Active and the previous card's Default designation is cleared within the resolved scope."
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
        as: "new-card"
        to: "Active"
      - entity: "rate-card"
        effect: "changes"
        facts:
          - "Default"
        as: "prior-card"
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

# New default card

## Trigger

Create a price list as the new scoped default while another default exists.

## Outcome

A Rate card is created as Active and the previous card's Default designation is cleared within the resolved scope.
