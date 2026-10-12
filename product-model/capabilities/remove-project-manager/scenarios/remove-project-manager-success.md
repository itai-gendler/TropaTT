---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Clear the current record assignment."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::project-detail"
      rest-work:
        place: "rest::work"
  - text: "The Project responsible person assignment becomes empty."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "project"
        effect: "changes"
        facts:
          - "Manager"
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

# Remove project manager: successful operation

## Trigger

Clear the current manager assignment.

## Outcome

The Project manager assignment becomes empty.
