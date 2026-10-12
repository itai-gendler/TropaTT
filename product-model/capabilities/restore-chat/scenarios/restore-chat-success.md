---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request restoration of the supported conversation previously archived by the current person."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::chat"
      rest-work:
        place: "rest::work"
  - text: "The Chat becomes active with supported participation restored."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "chat"
        effect: "changes"
        facts:
          - "Archived at"
          - "Archived by"
        from: "Archived"
        to: "Active"
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

# Restore chat: successful operation

## Trigger

Request restoration of the supported conversation previously archived by the current person.

## Outcome

The Chat becomes active with supported participation restored.
