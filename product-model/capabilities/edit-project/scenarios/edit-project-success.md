---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply supported record metadata and, optionally, its current positive revision."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::project-detail"
      rest-work:
        place: "rest::work"
  - text: "The Project metadata changes and its revision advances."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "project"
        effect: "changes"
        facts:
          - "Title"
          - "Description"
          - "Priority"
          - "Start date"
          - "Due date"
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

# Edit project: successful operation

## Trigger

Supply supported project metadata and, optionally, its current positive revision.

## Outcome

The Project metadata changes and its revision advances.
