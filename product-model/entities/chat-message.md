---
domain: "chat"
relations:
  - entity: "chat-history"
    verb: "has-history"
    cardinality: "one-to-many"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ChatService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/chat/ChatController.php"
---

# Chat message

Chat/sender/body/reply/request identity/edit/deletion facts.

## Information kept

- **Body** — Message content.
- **Sender** — Sending person.
- **Reply** — Optional parent message.
- **Request identity** — Caller-supplied retry identity.
- **Created at** — Send time.
- **Edited at** — Edit time.
- **Deleted at** — Logical deletion time.
