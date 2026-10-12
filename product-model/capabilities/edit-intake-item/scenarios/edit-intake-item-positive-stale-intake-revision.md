---
kind: "edge"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Edit incoming metadata supplying a positive stale revision."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "The preliminary revision conflicts before saving the requested ordinary changes."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/IntakeItemService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/intake/IntakeItemController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/intake/IntakeItemRepository.php"
---

# Positive stale intake revision

## Trigger

Edit incoming metadata supplying a positive stale revision.

## Outcome

The preliminary revision conflicts before saving the requested ordinary changes.
