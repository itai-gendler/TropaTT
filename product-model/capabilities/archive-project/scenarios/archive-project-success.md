---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Confirm archival of the selected record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::project-detail"
      rest-work:
        place: "rest::work"
  - text: "The Project is archived and the browser returns from detail to the project collection."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "project"
        effect: "changes"
        facts:
          - "Archived at"
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

# Archive project: successful operation

## Trigger

Confirm archival of the selected project.

## Outcome

The Project is archived and the browser returns from detail to the project collection.
