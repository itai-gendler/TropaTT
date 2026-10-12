---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Mark an own recipient message read."
    kind: "actor"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::notifications"
      rest-work:
        place: "rest::work::notifications"
  - text: "The Notification becomes Read."
    kind: "product"
    actor: "external-observer"
    entities:
      - entity: "notification"
        effect: "changes"
        facts:
          - "Read"
        from: "Unread"
        to: "Read"
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

# Mark notification read as external observer

## Trigger

Mark an own recipient message read.

## Outcome

The Notification becomes Read.
