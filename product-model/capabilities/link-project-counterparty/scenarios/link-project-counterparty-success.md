---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select a reachable customer or business record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::project-detail"
      rest-work:
        place: "rest::work"
  - text: "The Project business-context link is saved."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "project"
        effect: "changes"
        facts:
          - "Counterparty"
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

# Link project counterparty: successful operation

## Trigger

Select a reachable customer or business record.

## Outcome

The Project business-context link is saved.
