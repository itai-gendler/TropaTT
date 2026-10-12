---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "An unavailable request cannot be unassigned."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "An unavailable request cannot be unassigned."
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

# Unassign intake item: refused or unavailable operation

## Trigger

An unavailable request cannot be unassigned.

## Outcome

An unavailable request cannot be unassigned.
