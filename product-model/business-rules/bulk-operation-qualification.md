---
appliesTo:
  - type: "capability"
    id: "change-task-status"
  - type: "capability"
    id: "assign-task"
  - type: "capability"
    id: "unassign-task"
  - type: "capability"
    id: "set-task-parent"
  - type: "capability"
    id: "remove-task-parent"
  - type: "capability"
    id: "archive-task"
  - type: "capability"
    id: "restore-task"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/task/TaskController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/TaskService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/task/TaskRepository.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/support/TaskStatusSemantics.php"
---

# Bulk Task operations retain partial outcomes

Bulk Task processing records per-item successes and failures and can leave successful earlier items changed when another fails. Its notification/status hook reads the top-level input status while ordinary bulk changes are nested in changes.status; normal item mutation is not evidence that every bulk status notification ran.
