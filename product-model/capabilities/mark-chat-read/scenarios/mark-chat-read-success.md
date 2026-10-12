---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Submit the read position of the selected participating conversation."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::chat"
      rest-work:
        place: "rest::work"
  - text: "The current Chat membership read position advances."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "chat-membership"
        effect: "changes"
        facts:
          - "Read position"
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

# Mark chat read: successful operation

## Trigger

Submit the read position of the selected participating conversation.

## Outcome

The current Chat membership read position advances.
