---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply replacement text for an own message within the edit window."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::chat"
      rest-work:
        place: "rest::work"
  - text: "Chat message content changes and displayed change history is recorded."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "chat-message"
        effect: "changes"
        facts:
          - "Body"
          - "Edited at"
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

# Edit chat message: successful operation

## Trigger

Supply replacement text for an own message within the edit window.

## Outcome

Chat message content changes and displayed change history is recorded.
