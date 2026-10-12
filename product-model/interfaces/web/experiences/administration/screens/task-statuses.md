---
entities:
  - entity: "task-status"
    shows:
      - "Code"
      - "Title"
      - "Order"
      - "Active"
      - "Terminal"
      - "WIP limit"
      - "Organization"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Task statuses

Task-scope runtime dictionary titles, codes, flags, ordering and WIP limits.
