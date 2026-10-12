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
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Notifications

Recipient notification records, destinations and read state.
