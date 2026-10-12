---
domain: "tasks"
relations:
  - entity: "task-tag-assignment"
    verb: "is-applied-through"
    cardinality: "one-to-many"
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
---

# Tag

Runtime title and organization context; full dictionary lifecycle unmapped.

## Information kept

- **Title** — Runtime tag title.
- **Organization** — Tag dictionary workspace.
