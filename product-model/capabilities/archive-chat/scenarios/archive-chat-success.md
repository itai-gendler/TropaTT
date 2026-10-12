---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request archival of a supported participating conversation created by the current person."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::chat"
      rest-work:
        place: "rest::work"
  - text: "The Chat becomes archived and restoration information is retained."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "chat"
        effect: "changes"
        facts:
          - "Archived at"
          - "Archived by"
        from: "Active"
        to: "Archived"
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

# Archive chat: successful operation

## Trigger

Request archival of a supported participating conversation created by the current person.

## Outcome

The Chat becomes archived and restoration information is retained.
