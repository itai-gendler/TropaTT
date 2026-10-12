---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "An unavailable conversation cannot accept a read position."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::chat"
      rest-work:
        place: "rest::work"
  - text: "An unavailable conversation cannot accept a read position."
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

# Mark chat read: refused or unavailable operation

## Trigger

An unavailable conversation cannot accept a read position.

## Outcome

An unavailable conversation cannot accept a read position.
