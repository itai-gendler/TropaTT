---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Reject the pending review of the selected page."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "The Knowledge page returns to Draft with its rejection designation."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "knowledge-page"
        effect: "changes"
        facts:
          - "Review"
          - "Revision"
        from: "Review"
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

# Reject page review: successful operation

## Trigger

Reject the pending review of the selected page.

## Outcome

The Knowledge page returns to Draft with its rejection designation.
