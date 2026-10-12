---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "An unavailable request cannot receive assignment."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "An unavailable request cannot receive assignment."
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

# Assign intake item: refused or unavailable operation

## Trigger

An unavailable request cannot receive assignment.

## Outcome

An unavailable request cannot receive assignment.
