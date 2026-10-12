---
entities:
  - entity: "task"
    shows:
      - "Key"
      - "Title"
      - "Status"
      - "Priority"
      - "Assignee"
      - "Due date"
      - "Project"
  - entity: "calendar-event"
    shows:
      - "Title"
      - "Description"
      - "Owner"
      - "Starts at"
      - "Ends at"
      - "Work"
      - "Source"
      - "Privacy"
  - entity: "event-attendance"
    shows:
      - "Account"
      - "Designation"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# My week

Calculated agenda and due-work summaries for the named period.
