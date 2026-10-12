---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
  web-detail: "Web Detail"
steps:
  - text: "An unavailable record returns the addressed-record not-found result or is absent from the list."
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
  - text: "An unavailable record returns the addressed-record not-found result or is absent from the list."
    kind: "condition"
    actor: "root-administrator"
    entities: []
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

# Browse projects: refused or unavailable operation

## Trigger

An unavailable project returns PROJECT_NOT_FOUND or is absent from the list.

## Outcome

An unavailable project returns PROJECT_NOT_FOUND or is absent from the list.
