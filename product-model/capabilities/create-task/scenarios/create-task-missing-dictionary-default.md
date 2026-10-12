---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Create work without an explicit status when no active nonterminal dictionary default is found."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::task-record"
  - text: "A Task is created with status new and the other supported creation defaults."
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
      rest-work:
        place: "rest::work::task-record"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/task/TaskController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/TaskService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/task/TaskRepository.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/support/TaskStatusSemantics.php"
---

# Missing dictionary default

## Trigger

Create work without an explicit status when no active nonterminal dictionary default is found.

## Outcome

A Task is created with status new and the other supported creation defaults.
