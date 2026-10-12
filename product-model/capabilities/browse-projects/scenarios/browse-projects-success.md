---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
  web-detail: "Web Detail"
steps:
  - text: "Read the record list or selected record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::projects"
      rest-work:
        place: "rest::work"
      web-detail:
        place: "web::work::project-detail"
  - text: "Project facts, assignments and business links are returned."
    kind: "product"
    actor: "root-administrator"
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
      web-work:
        place: "web::work::projects"
      rest-work:
        place: "rest::work"
      web-detail:
        place: "web::work::project-detail"
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

# Browse projects: successful operation

## Trigger

Read the project list or selected project.

## Outcome

Project facts, assignments and business links are returned.
