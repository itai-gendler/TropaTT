---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Accept a Pending request with supported record-conversion input."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::intake"
      rest-work:
        place: "rest::work"
  - text: "A Task is created from the request before its resolution is persisted."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task"
        effect: "creates"
        facts:
          - "Key"
          - "Title"
          - "Description"
          - "Status"
          - "Priority"
          - "Activity"
          - "Start date"
          - "Due date"
          - "Revision"
          - "Archived at"
          - "Deleted at"
          - "Creator"
          - "Assignee"
          - "Project"
          - "Counterparty"
          - "Parent"
          - "Cost rate"
          - "Bill rate"
          - "Payout rate"
          - "Currency"
    contexts:
      web-work:
        place: "web::work::intake"
      rest-work:
        place: "rest::work"
  - text: "The Intake item then records the accepted resolution and created-work reference."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "intake-item"
        effect: "changes"
        facts:
          - "Resolution"
          - "Task"
          - "Revision"
        from: "Pending"
        to: "Accepted"
    contexts:
      web-work:
        place: "web::work::intake"
      rest-work:
        place: "rest::work"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/IntakeItemService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/intake/IntakeItemController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/intake/IntakeItemRepository.php"
---

# Accept intake item: successful operation

## Trigger

Accept a Pending request with supported task-conversion input.

## Outcome

A Task is created before the Intake item becomes Accepted and linked to it.
