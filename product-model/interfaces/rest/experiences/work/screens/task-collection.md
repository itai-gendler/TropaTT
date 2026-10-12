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
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/app.php"
---

# Task collection

Work listing, filtering and record summaries; ordinary response financial filtering is operation-specific.
