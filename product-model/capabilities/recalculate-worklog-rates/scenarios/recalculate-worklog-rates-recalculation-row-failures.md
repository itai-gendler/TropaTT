---
kind: "edge"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Recalculate a valid unlocked batch where some rows fail resolution."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::time-reports"
  - text: "Worklog rate snapshots change for successful rows; processed/failed counts report partial processing without a whole-batch success guarantee."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "worklog"
        effect: "changes"
        facts:
          - "Cost rate"
          - "Bill rate"
          - "Payout rate"
          - "Currency"
          - "Provenance"
    contexts:
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

# Recalculation row failures

## Trigger

Recalculate a valid unlocked batch where some rows fail resolution.

## Outcome

Worklog rate snapshots change for successful rows; processed/failed counts report partial processing without a whole-batch success guarantee.
