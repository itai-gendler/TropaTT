---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Read access entries of the selected space."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "Space permission subjects and access levels are returned."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "space-permission"
        effect: "reads"
        facts:
          - "Subject"
          - "Access level"
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

# Browse space permissions: successful operation

## Trigger

Read access entries of the selected space.

## Outcome

Space permission subjects and access levels are returned.
