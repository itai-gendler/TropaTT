---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Choose a valid exact period with matching scoped time entries."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::time-reports"
  - text: "Worklog entries become locked and the exact global period is registered."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "worklog"
        effect: "changes"
        facts:
          - "Locked"
        from: "Unlocked"
        to: "Locked"
      - entity: "rate-locked-period"
        effect: "creates"
        facts:
          - "From"
          - "To"
      - entity: "finance-settings"
        effect: "changes"
        facts:
          - "Locked ranges"
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::time-reports"
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

# Lock rate period: successful operation

## Trigger

Choose a valid exact period with matching scoped time entries.

## Outcome

Worklog entries become locked and the exact global period is registered.
