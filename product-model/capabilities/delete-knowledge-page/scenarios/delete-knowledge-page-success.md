---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Delete the selected saved page through its supported logical-removal path."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "The Knowledge page is logically removed."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "knowledge-page"
        effect: "removes"
        from: "Draft"
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

# Delete knowledge page: successful operation

## Trigger

The addressed knowledge page starts Draft. Delete the selected saved page through its supported logical-removal path.

## Outcome

The Knowledge page is logically removed.
