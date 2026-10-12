---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply nonempty message content and supported reply information."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::chat"
      rest-work:
        place: "rest::work"
  - text: "A Chat message is saved and returned; a requested outbound assistant continuation is separate from persistence."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "chat-message"
        effect: "creates"
        facts:
          - "Body"
          - "Sender"
          - "Reply"
          - "Request identity"
          - "Created at"
          - "Edited at"
          - "Deleted at"
    contexts:
      web-work:
        place: "web::work::chat"
      rest-work:
        place: "rest::work"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ChatService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/chat/ChatController.php"
---

# Send chat message: successful operation

## Trigger

Supply nonempty message content and supported reply information.

## Outcome

A Chat message is saved and returned; a requested outbound assistant continuation is separate from persistence.
