---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Submit ordinary saved-page editing with status published, without mandatory prior review."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "The Knowledge page becomes Published through ordinary editing and a Knowledge version is saved; explicit publication metadata is not implied."
    kind: "product"
    actor: "administrator"
    entities:
      - entity: "knowledge-page"
        effect: "changes"
        facts:
          - "Revision"
        to: "Published"
        from: "Draft"
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

# Ordinary status edit

## Trigger

The addressed page starts in Draft. Submit ordinary saved-page editing with status published, without mandatory prior review.

## Outcome

The Knowledge page becomes Published through ordinary editing and a Knowledge version is saved; explicit publication metadata is not implied.
