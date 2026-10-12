---
entities:
  - entity: "chat"
    shows:
      - "Kind"
      - "Title"
      - "Creator"
      - "Organization"
      - "Archived at"
      - "Archived by"
  - entity: "chat-membership"
    shows:
      - "Account"
      - "Role"
      - "Joined at"
      - "Read position"
      - "Restoration information"
  - entity: "chat-message"
    shows:
      - "Body"
      - "Sender"
      - "Reply"
      - "Request identity"
      - "Created at"
      - "Edited at"
      - "Deleted at"
  - entity: "chat-history"
    shows:
      - "Actor"
      - "Previous content"
      - "New content"
      - "Created at"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Chat

Selected conversation, participants, messages, replies, displayed history, read position and archival.
