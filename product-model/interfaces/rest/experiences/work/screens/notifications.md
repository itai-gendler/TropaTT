---
entities:
  - entity: "notification"
    shows:
      - "Recipient"
      - "Event"
      - "Title"
      - "Body"
      - "Link"
      - "Created at"
      - "Read"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/app.php"
---

# Notifications

Recipient records and explicit read-state operations.
