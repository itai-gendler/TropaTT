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
  - entity: "organization-invitation"
    shows:
      - "Email"
      - "Role"
      - "Inviter"
      - "Expires at"
      - "Accepted at"
      - "Revoked at"
  - entity: "account"
    shows:
      - "Login"
      - "Name"
      - "Email"
      - "Active"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/app.php"
---

# Organization directory

Workspace, membership and organization-invitation records and operation results.
