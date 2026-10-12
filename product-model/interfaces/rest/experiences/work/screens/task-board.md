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
      - "Cost rate"
      - "Bill rate"
      - "Payout rate"
      - "Currency"
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
    target: "upload/api/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/app.php"
---

# Task board

Status-column work projections and dedicated movement outcomes.
