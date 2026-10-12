---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request work containers for the linked customer."
    kind: "actor"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::projects"
      rest-work:
        place: "rest::work"
  - text: "Project records for the linked customer are returned."
    kind: "product"
    actor: "external-observer"
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

# Browse projects as external observer

## Trigger

Request projects for the linked customer.

## Outcome

Project records for the linked customer are returned.
