---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Move a non-system space to trash."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::knowledge"
      rest-work:
        place: "rest::work"
  - text: "Knowledge space subtree records are trashed; the count of nondeleted Knowledge pages is read for the hidden-page outcome."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "knowledge-space"
        effect: "changes"
        facts:
          - "Deleted at"
          - "Revision"
      - entity: "knowledge-page"
        effect: "reads"
        facts:
          - "Deleted at"
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
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/knowledge/KnowledgeRepository.php#trashSpace"
---

# Delete knowledge space: successful operation

## Trigger

Move a non-system space to trash.

## Outcome

The Knowledge space subtree is trashed and live contained pages are hidden.
