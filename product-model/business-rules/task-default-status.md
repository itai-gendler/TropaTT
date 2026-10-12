---
appliesTo:
  - type: "capability"
    id: "create-task"
    contexts:
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

# New Tasks use the implemented unscoped default status

Task creation chooses the first active, nonterminal task-scope dictionary status by its implemented order, using an unscoped query; when no candidate exists it falls back to new. The choice does not establish organization precedence among duplicate codes.
