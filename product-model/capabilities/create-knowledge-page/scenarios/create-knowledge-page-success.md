---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a title, saved content and an editable destination, using Draft status."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::knowledge-page"
      rest-work:
        place: "rest::work"
  - text: "A draft Knowledge page is kept and its saved version is addressed."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "knowledge-page"
        effect: "creates"
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
        to: "Draft"
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
        with: "knowledge-page"
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

# Create knowledge page: successful operation

## Trigger

Supply a title, saved content and an editable destination, using Draft status.

## Outcome

A draft Knowledge page is kept and its saved version is addressed.
