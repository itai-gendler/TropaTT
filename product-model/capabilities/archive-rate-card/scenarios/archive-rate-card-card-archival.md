---
kind: "edge"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Archive a price list with active target assignments."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::rate-cards"
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "Rate card Archived at changes and Rate-card assignment entries are removed."
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

# Card archival

## Trigger

Archive a price list with active target assignments.

## Outcome

Rate card Archived at changes and Rate-card assignment entries are removed.
