---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request deletion of an own message within its deletion window."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::chat"
      rest-work:
        place: "rest::work"
  - text: "The Chat message receives its logical deletion designation and history is recorded."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "chat-message"
        effect: "removes"
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

# Delete chat message: successful operation

## Trigger

Request deletion of an own message within its deletion window.

## Outcome

The Chat message receives its logical deletion designation and history is recorded.
