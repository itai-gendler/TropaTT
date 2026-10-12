---
appliesTo:
  - type: "capability"
    id: "set-task-parent"
  - type: "capability"
    id: "remove-task-parent"
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

# Parent changes reject the guarded graph conflicts

Parent mutation rejects self-parenting and cycles, validates applicable parent/project access and applies the ordinary graph/related-parent lease fences. Clearing or restoring a parent is an operation on the existing work graph, not a guarantee that every historical relationship is valid.
