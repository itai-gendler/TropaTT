---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Mark an addressed recipient message unread."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::notifications"
      rest-work:
        place: "rest::work::notifications"
  - text: "The Notification becomes Unread."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "notification"
        effect: "changes"
        facts:
          - "Read"
        from: "Read"
        to: "Unread"
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

# Mark notification unread: successful operation

## Trigger

Mark an addressed recipient message unread.

## Outcome

The Notification becomes Unread.
