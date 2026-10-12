---
kind: "edge"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Send valid content to an addressed built-in assistant conversation while its outbound assistant continuation is unavailable."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::chat"
      rest-work:
        place: "rest::work"
  - text: "The Chat message remains saved; the assistant failure or lack of continuation does not undo message persistence."
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

# Addressed built-in AI unavailable

## Trigger

Send valid content to an addressed built-in assistant conversation while its outbound assistant continuation is unavailable.

## Outcome

The Chat message remains saved; the assistant failure or lack of continuation does not undo message persistence.
