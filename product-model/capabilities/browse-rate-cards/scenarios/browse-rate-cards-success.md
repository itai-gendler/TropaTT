---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read scoped price lists, selector lines and assignments."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::rate-cards"
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "Rate card records and their line and assignment facts are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "rate-card"
        effect: "reads"
        facts:
          - "Title"
          - "Description"
          - "Currency"
          - "Default"
          - "Archived at"
          - "Created at"
      - entity: "rate-card-line"
        effect: "reads"
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
      - entity: "rate-card-assignment"
        effect: "reads"
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

# Browse rate cards: successful operation

## Trigger

Read scoped price lists, selector lines and assignments.

## Outcome

Rate card records and their line and assignment facts are returned.
