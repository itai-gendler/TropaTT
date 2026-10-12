---
appliesTo:
  - type: "capability"
    id: "create-task"
  - type: "capability"
    id: "edit-task"
  - type: "capability"
    id: "change-task-status"
  - type: "capability"
    id: "move-task"
  - type: "capability"
    id: "create-subtask"
  - type: "capability"
    id: "edit-subtask"
  - type: "capability"
    id: "change-subtask-status"
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
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/subtask/SubtaskController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/SubtaskService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/subtask/SubtaskRepository.php"
---

# Accepted statuses depend on the entry point

Status acceptance depends on entry point. Ordinary Task creation/editing accepts the canonical codes and the custom codes its validation looks up; scoped custom-status validation is not the unscoped dedicated movement/board behavior. Subtasks accept the canonical nine-code set and do not inherit arbitrary custom Task statuses. Dictionary active flags do not uniformly prohibit canonical input on every route.
