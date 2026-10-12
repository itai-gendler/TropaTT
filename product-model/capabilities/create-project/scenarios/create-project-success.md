---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply title, unique prefix and supported record metadata."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::projects"
      rest-work:
        place: "rest::work"
  - text: "A Project is created with supplied facts and creation defaults."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "project"
        effect: "creates"
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
      web-work:
        place: "web::work::projects"
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

# Create project: successful operation

## Trigger

Supply title, unique prefix and supported project metadata.

## Outcome

A Project is created with supplied facts and creation defaults.
