---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Create a direct conversation for a pair already having a supported direct conversation."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "The existing Chat is reused rather than creating a second direct conversation."
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

# Existing direct pair

## Trigger

Create a direct conversation for a pair already having a supported direct conversation.

## Outcome

The existing Chat is reused rather than creating a second direct conversation.
