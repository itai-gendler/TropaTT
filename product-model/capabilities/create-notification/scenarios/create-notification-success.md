---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Supply an event kind, title, content and supported recipient context."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::notifications"
  - text: "An unread Notification is created."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "notification"
        effect: "creates"
        facts:
          - "Recipient"
          - "Event"
          - "Title"
          - "Body"
          - "Link"
          - "Created at"
          - "Read"
        to: "Unread"
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

# Create notification: successful operation

## Trigger

Supply an event kind, title, content and supported recipient context.

## Outcome

An unread Notification is created.
