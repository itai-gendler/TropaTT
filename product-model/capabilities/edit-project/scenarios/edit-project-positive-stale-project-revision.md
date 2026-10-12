---
kind: "edge"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Edit record metadata supplying a positive stale revision."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "ROW_VERSION_CONFLICT is returned and the attempted update is not saved."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
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

# Positive stale Project revision

## Trigger

Edit project metadata supplying a positive stale revision.

## Outcome

ROW_VERSION_CONFLICT is returned and the attempted update is not saved.
