---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "An unavailable or foreign-page version cannot be restored."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::knowledge-page"
      rest-work:
        place: "rest::work"
  - text: "An unavailable or foreign-page version cannot be restored."
    kind: "condition"
    actor: "administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::knowledge-page"
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

# Restore page version: refused or unavailable operation

## Trigger

An unavailable or foreign-page version cannot be restored.

## Outcome

An unavailable or foreign-page version cannot be restored.
