---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Choose a valid record status; completion has no remaining open work."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::project-detail"
      rest-work:
        place: "rest::work"
  - text: "The Project status changes."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "project"
        effect: "changes"
        facts:
          - "Status"
          - "Revision"
    contexts:
      web-work:
        place: "web::work::project-detail"
      rest-work:
        place: "rest::work"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/project/ProjectController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ProjectService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/project/ProjectRepository.php"
---

# Change project status: successful operation

## Trigger

Choose a valid project status; completion has no remaining open work.

## Outcome

The Project status changes.
