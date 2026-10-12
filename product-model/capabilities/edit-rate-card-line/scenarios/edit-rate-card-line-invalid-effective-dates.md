---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Edit a selector line with reversed or invalid effective dates."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "Effective-date validation refuses the edit."
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

# Invalid effective dates

## Trigger

Edit a selector line with reversed or invalid effective dates.

## Outcome

Effective-date validation refuses the edit.
