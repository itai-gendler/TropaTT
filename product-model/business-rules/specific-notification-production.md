---
appliesTo:
- type: entity
  id: notification
- type: entity
  id: task
- type: entity
  id: project
- type: entity
  id: calendar-event
- type: entity
  id: intake-item
references:
- kind: code
  role: implementation
  target: upload/api/system/library/service/NotificationService.php
- kind: code
  role: implementation
  target: upload/api/controller/task/TaskController.php
- kind: code
  role: implementation
  target: upload/api/controller/project/ProjectController.php
- kind: code
  role: implementation
  target: upload/api/system/library/service/CalendarService.php
- kind: code
  role: implementation
  target: upload/api/system/library/service/IntakeItemService.php
---

# Notifications follow only their actual producing paths

Only the traced Task, Project, Calendar and Intake source operations produce their implemented notification events and recipient sets. Best-effort hooks and path-specific dispatch do not establish universal delivery, exactly-once notification creation or atomicity with every source write.
