---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "An unavailable recipient record cannot be marked unread."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::notifications"
      rest-work:
        place: "rest::work::notifications"
  - text: "An unavailable recipient record cannot be marked unread."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::notifications"
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

# Mark notification unread: refused or unavailable operation

## Trigger

An unavailable recipient record cannot be marked unread.

## Outcome

An unavailable recipient record cannot be marked unread.
