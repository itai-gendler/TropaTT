---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read locked periods and auto-close configuration."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::time-reports"
  - text: "Rate-locked period records and financial configuration are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "rate-locked-period"
        effect: "reads"
        facts:
          - "From"
          - "To"
      - entity: "finance-settings"
        effect: "reads"
        facts:
          - "Auto-close"
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

# Browse rate periods: successful operation

## Trigger

Read locked periods and auto-close configuration.

## Outcome

Rate-locked period records and financial configuration are returned.
