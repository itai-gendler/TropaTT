---
actors:
  - "root-administrator"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/page-api-bindings.js"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/project/ProjectController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/task/TaskController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ProjectService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/TaskService.php"
---

# Complete a project with open tasks

## Goal

Resolve the open work exposed by the completion refusal and complete the same Project.

## Success criterion

The offered resolution succeeds for the addressed work and the Project's status becomes completed.
