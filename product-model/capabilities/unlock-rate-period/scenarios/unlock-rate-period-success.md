---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Choose a valid exact locked period with matching scoped time entries."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::time-reports"
  - text: "Worklog entries are unlocked and the exact global period is removed."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "worklog"
        effect: "changes"
        facts:
          - "Locked"
        from: "Locked"
        to: "Unlocked"
      - entity: "rate-locked-period"
        effect: "removes"
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

# Unlock rate period: successful operation

## Trigger

Choose a valid exact locked period with matching scoped time entries.

## Outcome

Worklog entries are unlocked and the exact global period is removed.
