---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select a belonging saved version and valid optional current revision for restoration."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::knowledge-page"
      rest-work:
        place: "rest::work"
  - text: "Knowledge page title/content are restored and a new version retains restoration provenance."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "knowledge-page"
        effect: "changes"
        facts:
          - "Title"
          - "Content"
      - entity: "knowledge-version"
        effect: "creates"
        facts:
          - "Title"
          - "Content"
          - "Number"
          - "Author"
          - "Created at"
          - "Change summary"
          - "Restoration provenance"
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

# Restore page version: successful operation

## Trigger

Select a belonging saved version and valid optional current revision for restoration.

## Outcome

Knowledge page title/content are restored and a new version retains restoration provenance.
