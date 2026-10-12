---
appliesTo:
  - type: "capability"
    id: "move-task"
    contexts:
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

# Dedicated movement retains its qualified WIP and revision checks

Dedicated movement applies its unscoped status lookup and WIP count only when the destination differs. The count includes nondeleted work without universally excluding archived work. Board status columns likewise do not establish organization precedence. Its supplied revision is checked preliminarily, but the controller does not forward all lease/fence context into the actual update. Web Kanban ordinary PATCH does not inherit this dedicated WIP check.
