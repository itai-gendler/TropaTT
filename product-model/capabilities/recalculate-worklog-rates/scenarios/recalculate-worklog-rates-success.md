---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Request a valid unlocked-entry recalculation batch with dry-run disabled."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::time-reports"
  - text: "Worklog rate snapshots are recalculated; processed and failed counts are returned."
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

# Recalculate worklog rates: successful operation

## Trigger

Request a valid unlocked-entry recalculation batch with dry-run disabled.

## Outcome

Worklog rate snapshots are recalculated; processed and failed counts are returned.
