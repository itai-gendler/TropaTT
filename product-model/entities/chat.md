---
domain: "chat"
relations:
  - entity: "chat-membership"
    verb: "has-participants"
    cardinality: "one-to-many"
  - entity: "chat-message"
    verb: "has-messages"
    cardinality: "one-to-many"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ChatService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/chat/ChatController.php"
---

# Chat

Kind/title/creator/organization/archive; participants; Active/Archived.

## Information kept

- **Kind** — Direct, group or other kept conversation classification.
- **Title** — Conversation title.
- **Creator** — Creating person.
- **Organization** — Workspace context.
- **Archived at** — Archival time.
- **Archived by** — Archiving person.

## States

### Active

The conversation is not archived.

### Archived

The conversation carries its archive time and archiving person; restoration follows its retained participant information.
