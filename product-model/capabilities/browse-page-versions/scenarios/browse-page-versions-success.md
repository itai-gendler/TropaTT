---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read the versions of the selected accessible page."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::knowledge-page"
      rest-work:
        place: "rest::work"
  - text: "Knowledge version snapshots, numbers, authors and notes are returned."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "knowledge-version"
        effect: "reads"
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

# Browse page versions: successful operation

## Trigger

Read the versions of the selected accessible page.

## Outcome

Knowledge version snapshots, numbers, authors and notes are returned.
