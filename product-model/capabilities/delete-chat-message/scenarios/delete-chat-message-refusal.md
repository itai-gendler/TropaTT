---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "An unavailable message cannot be deleted."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::chat"
      rest-work:
        place: "rest::work"
  - text: "An unavailable message cannot be deleted."
    kind: "condition"
    actor: "root-administrator"
    entities: []
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

# Delete chat message: refused or unavailable operation

## Trigger

An unavailable message cannot be deleted.

## Outcome

An unavailable message cannot be deleted.
