---
appliesTo:
  - type: "capability"
    id: "browse-tasks"
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

# Task filters expand the shipped status aliases

Task status filters expand the implemented new/todo, done/completed and canceled/cancelled aliases. Expansion is filter behavior rather than rewriting the kept Task status.
