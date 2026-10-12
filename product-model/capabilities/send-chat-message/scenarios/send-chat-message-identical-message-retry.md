---
kind: "edge"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Resend identical body and reply using the same record, sender and valid request identity."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "The earlier Chat message is replayed without a duplicate send."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "chat-message"
        effect: "reads"
        facts:
          - "Body"
          - "Sender"
          - "Reply"
          - "Request identity"
          - "Created at"
          - "Edited at"
          - "Deleted at"
    contexts:
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

# Identical message retry

## Trigger

Resend identical body and reply using the same chat, sender and valid request identity.

## Outcome

The earlier Chat message is replayed without a duplicate send.
