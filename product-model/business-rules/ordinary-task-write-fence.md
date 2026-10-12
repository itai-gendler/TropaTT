---
appliesTo:
  - type: "capability"
    id: "edit-task"
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

# Ordinary Task updates retain their actual write fence

Ordinary Task update paths use the MySQL READ COMMITTED write fence, acquiring the applicable lease/graph protection before locking the Task row. A positive supplied revision is compared and updated through the protected write; omitted/nonpositive revision does not establish compare-and-swap. Other drivers can report fence unavailability. Creation, deletion, Subtask writes and raw dictionary remapping are not assigned this whole contract. The dedicated move preliminary check does not forward its full fence context.
