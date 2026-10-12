---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Missing title or invalid input is rejected."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::projects"
      rest-work:
        place: "rest::work"
  - text: "Missing title or invalid input is rejected."
    kind: "condition"
    actor: "root-administrator"
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

# Create project: refused or unavailable operation

## Trigger

Missing title or invalid input is rejected.

## Outcome

Missing title or invalid input is rejected.
