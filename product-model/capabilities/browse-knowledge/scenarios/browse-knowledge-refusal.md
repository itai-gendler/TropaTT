---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
  web-page: "Web Page"
steps:
  - text: "Unavailable knowledge is absent from the listing or returns a not-found response."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::knowledge"
      rest-work:
        place: "rest::work"
      web-page:
        place: "web::work::knowledge-page"
  - text: "Unavailable knowledge is absent from the listing or returns a not-found response."
    kind: "condition"
    actor: "administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::knowledge"
      rest-work:
        place: "rest::work"
      web-page:
        place: "web::work::knowledge-page"
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

# Browse knowledge: refused or unavailable operation

## Trigger

Unavailable knowledge is absent from the listing or returns a not-found response.

## Outcome

Unavailable knowledge is absent from the listing or returns a not-found response.
