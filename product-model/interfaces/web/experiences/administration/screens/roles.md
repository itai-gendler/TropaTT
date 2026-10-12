---
entities:
  - entity: "role"
    shows:
      - "Code"
      - "Title"
      - "System"
  - entity: "role-permission"
    shows:
      - "Permission code"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Roles

Runtime roles and their configured permission entries.
