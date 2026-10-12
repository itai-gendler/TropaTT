---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read the current recipient's recipient messages and supported filters."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::notifications"
      rest-work:
        place: "rest::work::notifications"
  - text: "Notification records and read designations are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "notification"
        effect: "reads"
        facts:
          - "Recipient"
          - "Event"
          - "Title"
          - "Body"
          - "Link"
          - "Created at"
          - "Read"
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

# Browse notifications: successful operation

## Trigger

Read the current recipient's notifications and supported filters.

## Outcome

Notification records and read designations are returned.
