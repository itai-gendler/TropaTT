---
kind: "edge"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Unlock a valid period whose scoped row selection is empty."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::time-reports"
  - text: "The operation returns its empty result before removing a global range; existing global registration can remain."
    kind: "condition"
    actor: "root-administrator"
    entities: []
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

# Empty scoped unlock

## Trigger

Unlock a valid period whose scoped row selection is empty.

## Outcome

The operation returns its empty result before removing a global range; existing global registration can remain.
