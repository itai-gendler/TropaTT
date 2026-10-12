---
entities:
  - entity: "account"
    shows:
      - "Login"
      - "Name"
      - "Email"
      - "Active"
  - entity: "user-role-assignment"
    shows:
      - "Account"
      - "Role"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Users

Person identity and inspected runtime-role assignments.
