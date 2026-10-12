---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read personal recipient messages."
    kind: "actor"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::notifications"
      rest-work:
        place: "rest::work::notifications"
  - text: "Own Notification records are returned."
    kind: "product"
    actor: "external-observer"
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

# Browse notifications as external observer

## Trigger

Read personal recipient messages.

## Outcome

Own Notification records are returned.
