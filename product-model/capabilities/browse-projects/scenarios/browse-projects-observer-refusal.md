---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Foreign-customer work containers are absent or return the addressed-record not-found result."
    kind: "actor"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::projects"
      rest-work:
        place: "rest::work"
  - text: "Foreign-customer work containers are absent or return the addressed-record not-found result."
    kind: "condition"
    actor: "external-observer"
    entities: []
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

# Browse projects external observer boundary

## Trigger

Foreign-customer projects are absent or return PROJECT_NOT_FOUND.

## Outcome

Foreign-customer projects are absent or return PROJECT_NOT_FOUND.
