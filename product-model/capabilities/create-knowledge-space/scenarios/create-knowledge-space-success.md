---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a title, description and supported parent/access information."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::knowledge"
      rest-work:
        place: "rest::work"
  - text: "A Knowledge space is created within the readable/editable hierarchy."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "knowledge-space"
        effect: "creates"
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

# Create knowledge space: successful operation

## Trigger

Supply a title, description and supported parent/access information.

## Outcome

A Knowledge space is created within the readable/editable hierarchy.
