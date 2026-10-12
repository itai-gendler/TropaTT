---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "An unavailable page cannot be restored."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "An unavailable page cannot be restored."
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

# Restore knowledge page: refused or unavailable operation

## Trigger

An unavailable page cannot be restored.

## Outcome

An unavailable page cannot be restored.
