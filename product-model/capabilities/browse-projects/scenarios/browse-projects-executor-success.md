---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request granted work containers."
    kind: "actor"
    actor: "external-executor"
    entities: []
    contexts:
      web-work:
        place: "web::work::projects"
      rest-work:
        place: "rest::work"
  - text: "Project records in the explicit grant set are returned."
    kind: "product"
    actor: "external-executor"
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

# Browse projects as external executor

## Trigger

Request granted projects.

## Outcome

Project records in the explicit grant set are returned.
