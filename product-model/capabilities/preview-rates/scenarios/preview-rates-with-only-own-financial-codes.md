---
kind: "edge"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Request a valid rate preview using an internal own-only financial credential."
    kind: "actor"
    actor: "user"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::rate-card-lines"
  - text: "The route gate passes, but preview rows lack own-person identity; own-only fields are omitted from the result."
    kind: "condition"
    actor: "user"
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

# Own-only preview permission

## Trigger

Request a valid rate preview using an internal own-only financial credential.

## Outcome

The route gate passes, but preview rows lack own-person identity; own-only fields are omitted from the result.
