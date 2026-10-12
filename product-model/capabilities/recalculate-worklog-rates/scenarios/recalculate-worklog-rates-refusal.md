---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Invalid batch references or period input cannot start valid recalculation."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::time-reports"
  - text: "Invalid batch references or period input cannot start valid recalculation."
    kind: "condition"
    actor: "root-administrator"
    entities: []
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

# Recalculate worklog rates: refused or unavailable operation

## Trigger

Invalid batch references or period input cannot start valid recalculation.

## Outcome

Invalid batch references or period input cannot start valid recalculation.
