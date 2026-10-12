---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Missing event kind or invalid record input is rejected."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::notifications"
  - text: "Missing event kind or invalid record input is rejected."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::notifications"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/NotificationService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/notification/NotificationController.php"
---

# Create notification: refused or unavailable operation

## Trigger

Missing event kind or invalid notification input is rejected.

## Outcome

Missing event kind or invalid notification input is rejected.
