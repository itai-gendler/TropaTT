---
entities:
  - entity: "organization"
    shows:
      - "Title"
      - "Slug"
      - "Created at"
  - entity: "organization-membership"
    shows:
      - "Role"
      - "Joined at"
      - "Account"
  - entity: "account"
    shows:
      - "Name"
      - "Email"
      - "Active"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Organizations

Workspace selection, directory records and memberships.
