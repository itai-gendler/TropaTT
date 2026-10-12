---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request archival of a price list."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::rate-cards"
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "The Rate card becomes archived and its assignments are detached."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "rate-card"
        effect: "changes"
        facts:
          - "Archived at"
        from: "Active"
        to: "Archived"
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

# Archive rate card: successful operation

## Trigger

Request archival of a price list.

## Outcome

The Rate card becomes archived and its assignments are detached.
