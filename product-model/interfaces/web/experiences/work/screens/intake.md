---
entities:
- entity: intake-item
  shows:
  - Title
  - Description
  - Source
  - Context
  - Priority
  - Start date
  - Due date
  - Assignee
  - Revision
  - Resolution
  - Task
  - Duplicate
  - Creator
  collects:
  - Snoozed until
- entity: intake-activity
  shows:
  - Actor
  - Event
  - Field
  - Previous value
  - New value
  - Note
  - Created at
references:
- kind: code
  role: implementation
  target: upload/web/config/routes.php
- kind: code
  role: implementation
  target: upload/web/assets/js/br1.js
---

# Intake

Incoming requests, resolution outcomes, linked work and displayed activity. Detail remains within this subject.
