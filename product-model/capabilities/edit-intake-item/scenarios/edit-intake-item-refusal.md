---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Unsupported immutable or overlong ordinary input is rejected."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "Unsupported immutable or overlong ordinary input is rejected."
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

# Edit intake item: refused or unavailable operation

## Trigger

Unsupported immutable or overlong ordinary input is rejected.

## Outcome

Unsupported immutable or overlong ordinary input is rejected.
