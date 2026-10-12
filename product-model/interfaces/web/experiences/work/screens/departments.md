---
entities:
  - entity: "department"
    shows:
      - "Title"
      - "Code"
      - "Parent"
      - "Manager"
      - "Members"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Departments

Inspected department directory title, hierarchy, manager and members.
