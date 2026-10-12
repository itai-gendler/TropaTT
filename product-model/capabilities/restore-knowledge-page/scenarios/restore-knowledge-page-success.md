---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Restore an archived page through the explicit restoration path."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "The Knowledge page returns to Draft."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "knowledge-page"
        effect: "changes"
        facts:
          - "Revision"
        from: "Archived"
        to: "Draft"
    contexts:
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

# Restore knowledge page: successful operation

## Trigger

Restore an archived page through the explicit restoration path.

## Outcome

The Knowledge page returns to Draft.
