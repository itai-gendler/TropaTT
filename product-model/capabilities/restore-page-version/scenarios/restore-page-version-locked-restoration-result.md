---
kind: "edge"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Restore a belonging saved version while the page is locked."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::knowledge-page"
      rest-work:
        place: "rest::work"
  - text: "The service returns KNOWLEDGE_PAGE_LOCKED, but the controller has no matching refusal branch; its truthy result can enter the success envelope without title/content restoration."
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

# Locked restoration result

## Trigger

Restore a belonging saved version while the page is locked.

## Outcome

The service returns KNOWLEDGE_PAGE_LOCKED, but the controller has no matching refusal branch; its truthy result can enter the success envelope without title/content restoration.
