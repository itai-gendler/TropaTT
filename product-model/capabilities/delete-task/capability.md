---
availability:
  - place: "web::work"
  - place: "rest::work"
  - place: "mcp"
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

# Delete task

The Task is soft-deleted and direct child work is cascaded by the inspected deletion path. The agent contract accepts its advertised argument subset and delegates to the inspected controller.
