---
entities:
  - entity: "task"
    shows:
      - "Key"
      - "Title"
      - "Status"
      - "Priority"
      - "Assignee"
      - "Project"
      - "Revision"
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

# Kanban

Work by status. Browser movement updates ordinary status; it does not establish the dedicated movement WIP contract.
