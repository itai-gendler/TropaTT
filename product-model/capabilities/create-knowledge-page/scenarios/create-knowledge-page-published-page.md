---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Create a saved page with Published status in an editable destination."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "A Knowledge page starts Published with its saved Knowledge version; review is not a universal prerequisite."
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
        to: "Published"
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

# Published page

## Trigger

Create a saved page with Published status in an editable destination.

## Outcome

A Knowledge page starts Published with its saved Knowledge version; review is not a universal prerequisite.
