---
appliesTo:
- type: entity
  id: task
references:
- kind: code
  role: implementation
  target: upload/api/system/library/support/TaskStatusSemantics.php#isCompleted
---

# Successful completion is narrower than terminal status

Successful completion uses done, completed and closed, a narrower set than terminal classification. Canceled and archived work may be terminal without being successfully completed.
