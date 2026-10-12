---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Request archival of a live space."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "The Knowledge space receives archival information."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "knowledge-space"
        effect: "changes"
        facts:
          - "Archived at"
          - "Revision"
    contexts:
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

# Archive knowledge space: successful operation

## Trigger

Request archival of a live space.

## Outcome

The Knowledge space receives archival information.
