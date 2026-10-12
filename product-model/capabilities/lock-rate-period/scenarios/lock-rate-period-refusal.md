---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Invalid or reversed dates are rejected."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::time-reports"
  - text: "Invalid or reversed dates are rejected."
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

# Lock rate period: refused or unavailable operation

## Trigger

Invalid or reversed dates are rejected.

## Outcome

Invalid or reversed dates are rejected.
