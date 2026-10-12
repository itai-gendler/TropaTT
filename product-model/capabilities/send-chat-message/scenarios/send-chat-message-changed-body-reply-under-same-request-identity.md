---
kind: "edge"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Reuse the same message request identity with changed body or reply."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "The retry conflicts rather than replacing or duplicating the earlier message."
    kind: "condition"
    actor: "root-administrator"
    entities: []
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

# Changed body/reply under same request identity

## Trigger

Reuse the same message request identity with changed body or reply.

## Outcome

The retry conflicts rather than replacing or duplicating the earlier message.
