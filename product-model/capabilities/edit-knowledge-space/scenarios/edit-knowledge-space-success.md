---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply supported space metadata."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::knowledge"
      rest-work:
        place: "rest::work"
  - text: "Knowledge space metadata changes."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "knowledge-space"
        effect: "changes"
        facts:
          - "Title"
          - "Description"
          - "Parent"
          - "Visibility"
          - "Default access"
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

# Edit knowledge space: successful operation

## Trigger

Supply supported space metadata.

## Outcome

Knowledge space metadata changes.
