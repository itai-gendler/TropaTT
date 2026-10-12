---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Restore a trashed space while its stored parent remains trashed."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::knowledge"
      rest-work:
        place: "rest::work"
  - text: "Knowledge space Deleted at clears and Parent becomes empty, making the restored space independently reachable."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "knowledge-space"
        effect: "changes"
        facts:
          - "Deleted at"
          - "Parent"
          - "Revision"
    contexts:
      web-work:
        place: "web::work::knowledge"
      rest-work:
        place: "rest::work"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/knowledge/KnowledgeController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/knowledge/KnowledgeRepository.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/KnowledgePageVersionService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/knowledge/KnowledgePageVersionController.php"
---

# Restore under trashed parent

## Trigger

Restore a trashed space while its stored parent remains trashed.

## Outcome

Knowledge space Deleted at clears and Parent becomes empty, making the restored space independently reachable.
