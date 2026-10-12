---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Create child work with an explicitly selected accessible record differing from the inherited record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::task-record"
  - text: "A Subtask is created in the explicit work container with its parent and supported child defaults."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "subtask"
        effect: "creates"
        facts:
          - "Title"
          - "Description"
          - "Status"
          - "Priority"
          - "Due date"
          - "Order"
          - "Parent"
          - "Project"
          - "Assignee"
          - "Deleted at"
    contexts:
      rest-work:
        place: "rest::work::task-record"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/subtask/SubtaskController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/SubtaskService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/subtask/SubtaskRepository.php"
---

# Explicit accessible child Project

## Trigger

Create child work with an explicitly selected accessible project differing from the inherited project.

## Outcome

A Subtask is created in the explicit project with its parent and supported child defaults.
