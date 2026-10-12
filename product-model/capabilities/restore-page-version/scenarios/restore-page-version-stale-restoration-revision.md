---
kind: "edge"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Restore a belonging saved version supplying a stale preliminary page revision."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "ROW_VERSION_CONFLICT prevents title/content restoration."
    kind: "condition"
    actor: "administrator"
    entities: []
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

# Stale restoration revision

## Trigger

Restore a belonging saved version supplying a stale preliminary page revision.

## Outcome

ROW_VERSION_CONFLICT prevents title/content restoration.
