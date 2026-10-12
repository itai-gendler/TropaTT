---
entities:
  - entity: "task"
    shows:
      - "Key"
      - "Title"
      - "Description"
      - "Status"
      - "Priority"
      - "Activity"
      - "Start date"
      - "Due date"
      - "Revision"
      - "Archived at"
      - "Deleted at"
      - "Creator"
      - "Assignee"
      - "Project"
      - "Counterparty"
      - "Parent"
    collects:
      - "Title"
      - "Description"
      - "Status"
      - "Priority"
      - "Activity"
      - "Start date"
      - "Due date"
      - "Assignee"
      - "Project"
      - "Counterparty"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Tasks

Work collection with inspected filters and ordinary creation and mutation controls.
