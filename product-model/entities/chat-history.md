---
domain: "chat"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ChatService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/chat/ChatController.php"
---

# Chat history

Displayed actor/prior/new content/time for message changes/deletions.

## Information kept

- **Actor** — Person attributed to the change.
- **Previous content** — Prior displayed message content.
- **New content** — Resulting displayed content.
- **Created at** — Change time.
