---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "An unavailable line cannot be edited."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "An unavailable line cannot be edited."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
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

# Edit rate-card line: refused or unavailable operation

## Trigger

An unavailable line cannot be edited.

## Outcome

An unavailable line cannot be edited.
