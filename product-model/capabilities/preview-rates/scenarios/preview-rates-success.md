---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a person, date, activity and supported work context for a rate preview."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::rate-cards"
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "Independent cost, bill and payout resolution and a filtered provenance trace are returned without changing kept rates."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "account"
        effect: "reads"
        facts:
          - "Default cost rate"
          - "Default bill rate"
          - "Default payout rate"
          - "Currency"
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
      - entity: "task"
        effect: "reads"
        facts:
          - "Cost rate"
          - "Bill rate"
          - "Payout rate"
          - "Currency"
      - entity: "finance-settings"
        effect: "reads"
        facts:
          - "Currency"
          - "Markup"
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

# Preview rates: successful operation

## Trigger

Supply a person, date, activity and supported work context for a rate preview.

## Outcome

Independent cost, bill and payout resolution and a filtered provenance trace are returned without changing kept rates.
