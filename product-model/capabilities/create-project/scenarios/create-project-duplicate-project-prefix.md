---
kind: "edge"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Create a record using a prefix already held in the applicable prefix lookup."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::projects"
      rest-work:
        place: "rest::work"
  - text: "The duplicate prefix conflicts and no new record is created."
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

# Duplicate Project prefix

## Trigger

Create a project using a prefix already held in the applicable prefix lookup.

## Outcome

The duplicate prefix conflicts and no new project is created.
