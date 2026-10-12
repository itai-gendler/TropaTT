---
kind: "primary"
result: "achieved"
routes:
  web: "Web"
steps:
  - text: "Submit a title and valid participants for a new group conversation."
    kind: "actor"
    actor: "root-administrator"
    capability: "create-chat"
    entities: []
    contexts:
      web:
        place: "web::work::chat"
  - text: "The Chat and selected Chat membership records are created."
    kind: "product"
    actor: "root-administrator"
    capability: "create-chat"
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
      web:
        place: "web::work::chat"
  - text: "The Product selects the newly created conversation for this person."
    kind: "product"
    actor: "root-administrator"
    capability: "create-chat"
    entities: []
    contexts:
      web:
        place: "web::work::chat"
  - text: "Read the selected conversation."
    kind: "product"
    actor: "root-administrator"
    capability: "browse-chats"
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
      - entity: "chat-membership"
        effect: "reads"
        facts:
          - "Account"
          - "Role"
          - "Joined at"
          - "Read position"
          - "Restoration information"
    contexts:
      web:
        place: "web::work::chat"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/view/template/page/chat.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/page-api-bindings.js"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ChatService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/chat/ChatController.php"
---

# Open the newly created conversation

## Trigger

Submit a valid new group Chat in the Web conversation view.

## Outcome

The created Chat is selected and its conversation begins.
