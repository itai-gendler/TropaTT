---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read a participating conversation and its messages."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::chat"
      rest-work:
        place: "rest::work"
  - text: "Chat, participation, message and displayed history facts are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "chat"
        effect: "reads"
        facts:
          - "Kind"
          - "Title"
          - "Creator"
          - "Organization"
          - "Archived at"
          - "Archived by"
      - entity: "chat-membership"
        effect: "reads"
        facts:
          - "Account"
          - "Role"
          - "Joined at"
          - "Read position"
          - "Restoration information"
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
      - entity: "chat-history"
        effect: "reads"
        facts:
          - "Actor"
          - "Previous content"
          - "New content"
          - "Created at"
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

# Browse chats: successful operation

## Trigger

Read a participating conversation and its messages.

## Outcome

Chat, participation, message and displayed history facts are returned.
