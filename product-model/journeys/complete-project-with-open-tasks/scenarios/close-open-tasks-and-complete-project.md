---
kind: "primary"
result: "achieved"
routes:
  web: "Web"
steps:
  - text: "Request completion of the current work container."
    kind: "actor"
    actor: "root-administrator"
    capability: "change-project-status"
    entities: []
    contexts:
      web:
        place: "web::work::project-detail"
  - text: "Completion is refused and the dialog carries the person into open-work resolution."
    kind: "condition"
    actor: "root-administrator"
    capability: "change-project-status"
    entities: []
    contexts:
      web:
        place: "web::work::project-detail"
  - text: "Choose the offered close-open-work resolution."
    kind: "actor"
    actor: "root-administrator"
    capability: "change-project-status"
    entities: []
    contexts:
      web:
        place: "web::work::project-detail"
  - text: "Set the selected open work to done through bulk processing."
    kind: "product"
    actor: "root-administrator"
    capability: "change-task-status"
    entities:
      - entity: "task"
        effect: "changes"
        facts:
          - "Status"
          - "Revision"
    contexts:
      web:
        place: "web::work::project-detail"
  - text: "Retry completion of the original container after the successful resolution."
    kind: "actor"
    actor: "root-administrator"
    capability: "change-project-status"
    entities: []
    contexts:
      web:
        place: "web::work::project-detail"
  - text: "The Project is completed after the current open-work check succeeds."
    kind: "product"
    actor: "root-administrator"
    capability: "change-project-status"
    entities:
      - entity: "project"
        effect: "changes"
        facts:
          - "Status"
          - "Revision"
    contexts:
      web:
        place: "web::work::project-detail"
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

# Close open tasks and complete project

## Trigger

Request completion of an accessible Project whose current open tasks are within the resolution dialog's supported batch.

## Outcome

The Product offers resolution, applies the selected work changes and completes the original Project.

## Edge cases

- Pagination and the hardcoded open-status list limit which work the dialog resolves; partial bulk failure or remaining open work can prevent completion.
