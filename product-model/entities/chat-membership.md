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

# Chat membership

Chat–Account entry, participant Role/join/read position and restoration facts.

## Information kept

- **Account** — Participating person.
- **Role** — Participant designation.
- **Joined at** — Participation date.
- **Read position** — Last read message position.
- **Restoration information** — Participation information used by supported restoration.
