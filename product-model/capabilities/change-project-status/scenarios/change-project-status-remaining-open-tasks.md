---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request successful record completion while open, nondeleted and nonarchived work remains."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::project-detail"
      rest-work:
        place: "rest::work"
  - text: "Completion is refused and the browser offers closing or moving the remaining work before retrying."
    kind: "condition"
    actor: "root-administrator"
    entities: []
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

# Remaining open Tasks

## Trigger

Request successful project completion while open, nondeleted and nonarchived work remains.

## Outcome

Completion is refused and the browser offers closing or moving the remaining work before retrying.
