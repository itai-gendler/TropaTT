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

# Archive a project and return to projects

## Goal

Archive the current Project and continue in the collection selected by the Product.

## Success criterion

The Project is archived and the remaining Projects are read.
