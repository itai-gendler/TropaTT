---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a valid group title and selected participants."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::chat"
      rest-work:
        place: "rest::work"
  - text: "A group Chat and participant entries are created; the browser selects the conversation."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "chat"
        effect: "creates"
        facts:
          - "Kind"
          - "Title"
          - "Creator"
          - "Organization"
          - "Archived at"
          - "Archived by"
        to: "Active"
      - entity: "chat-membership"
        effect: "creates"
        facts:
          - "Account"
          - "Role"
          - "Joined at"
          - "Read position"
          - "Restoration information"
        with: "chat"
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

# Create chat: successful operation

## Trigger

Supply a valid group title and selected participants.

## Outcome

A group Chat and participant entries are created; the browser selects the conversation.
