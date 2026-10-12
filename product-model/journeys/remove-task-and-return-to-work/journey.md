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

# Remove a task and return to work

## Goal

Remove the addressed Task and continue in the work collection selected by the Product.

## Success criterion

Task removal returns the person to Tasks and the remaining work is read.
