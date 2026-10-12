---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request review of the selected saved page."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::knowledge-page"
      rest-work:
        place: "rest::work"
  - text: "The Knowledge page enters Review and its request metadata is recorded."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "knowledge-page"
        effect: "changes"
        facts:
          - "Review"
          - "Revision"
        to: "Review"
        from: "Draft"
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

# Request page review: successful operation

## Trigger

The addressed page starts in Draft. Request review of the selected saved page.

## Outcome

The Knowledge page enters Review and its request metadata is recorded.
