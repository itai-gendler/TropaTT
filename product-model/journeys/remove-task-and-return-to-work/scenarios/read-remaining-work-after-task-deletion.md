---
kind: "primary"
result: "achieved"
routes:
  web: "Web"
steps:
  - text: "Confirm removal of the addressed work item."
    kind: "actor"
    actor: "root-administrator"
    capability: "delete-task"
    entities: []
    contexts:
      web:
        place: "web::work::task-detail"
  - text: "The Task and direct Subtask records are logically removed."
    kind: "product"
    actor: "root-administrator"
    capability: "delete-task"
    entities:
      - entity: "task"
        effect: "removes"
      - entity: "subtask"
        effect: "removes"
        with: "task"
    contexts:
      web:
        place: "web::work::task-detail"
  - text: "The Product returns the person to the work collection."
    kind: "product"
    actor: "root-administrator"
    capability: "delete-task"
    entities: []
    contexts:
      web:
        place: "web::work::tasks"
  - text: "Remaining Tasks are read with the ordinary response policy."
    kind: "product"
    actor: "root-administrator"
    capability: "browse-tasks"
    entities:
      - entity: "task"
        effect: "reads"
        facts:
          - "Key"
          - "Title"
          - "Description"
          - "Status"
          - "Priority"
          - "Activity"
          - "Start date"
          - "Due date"
          - "Revision"
          - "Archived at"
          - "Deleted at"
          - "Creator"
          - "Assignee"
          - "Project"
          - "Counterparty"
          - "Parent"
          - "Cost rate"
          - "Bill rate"
          - "Payout rate"
          - "Currency"
    contexts:
      web:
        place: "web::work::tasks"
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

# Read remaining work after task deletion

## Trigger

Confirm removal from the Web Task detail view.

## Outcome

The addressed Task is logically removed and the Product returns the person to Tasks.
