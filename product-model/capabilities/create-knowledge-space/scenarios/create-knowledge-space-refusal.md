---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Missing or overlong title or invalid parent input prevents creation."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::knowledge"
      rest-work:
        place: "rest::work"
  - text: "Missing or overlong title or invalid parent input prevents creation."
    kind: "condition"
    actor: "administrator"
    entities: []
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

# Create knowledge space: refused or unavailable operation

## Trigger

Missing or overlong title or invalid parent input prevents creation.

## Outcome

Missing or overlong title or invalid parent input prevents creation.
