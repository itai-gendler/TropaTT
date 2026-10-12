---
kind: "primary"
result: "achieved"
routes:
  web: "Web"
steps:
  - text: "Confirm archival of the addressed work container."
    kind: "actor"
    actor: "root-administrator"
    capability: "archive-project"
    entities: []
    contexts:
      web:
        place: "web::work::project-detail"
  - text: "The Project's archive date and revision are changed."
    kind: "product"
    actor: "root-administrator"
    capability: "archive-project"
    entities:
      - entity: "project"
        effect: "changes"
        facts:
          - "Archived at"
          - "Revision"
    contexts:
      web:
        place: "web::work::project-detail"
  - text: "The Product returns the person to the container collection."
    kind: "product"
    actor: "root-administrator"
    capability: "archive-project"
    entities: []
    contexts:
      web:
        place: "web::work::projects"
  - text: "Remaining Projects are read."
    kind: "product"
    actor: "root-administrator"
    capability: "browse-projects"
    entities:
      - entity: "project"
        effect: "reads"
        facts:
          - "Title"
          - "Description"
          - "Status"
          - "Priority"
          - "Start date"
          - "Due date"
          - "Prefix"
          - "Revision"
          - "Archived at"
          - "Creator"
          - "Manager"
          - "Team"
          - "Counterparty"
    contexts:
      web:
        place: "web::work::projects"
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

# Read remaining projects after archival

## Trigger

Confirm archival from the Web Project detail view.

## Outcome

The Project is archived and the Product returns the person to Projects.
