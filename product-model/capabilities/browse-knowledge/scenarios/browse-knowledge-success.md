---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
  web-page: "Web Page"
steps:
  - text: "Read visible knowledge hierarchy and selected saved pages."
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
  - text: "Knowledge space and page facts are returned under authenticated ranked access."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "knowledge-space"
        effect: "reads"
        facts:
          - "Title"
          - "Description"
          - "Parent"
          - "Owner"
          - "Visibility"
          - "Default access"
          - "Revision"
          - "Archived at"
          - "Deleted at"
          - "System"
      - entity: "knowledge-page"
        effect: "reads"
        facts:
          - "Title"
          - "Content"
          - "Type"
          - "Parent"
          - "Owner"
          - "Client visible"
          - "Revision"
          - "Review"
          - "Publication"
          - "Deleted at"
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

# Browse knowledge: successful operation

## Trigger

Read visible knowledge hierarchy and selected saved pages.

## Outcome

Knowledge space and page facts are returned under authenticated ranked access.
