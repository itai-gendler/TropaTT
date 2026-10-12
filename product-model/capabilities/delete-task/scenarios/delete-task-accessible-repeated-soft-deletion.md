---
kind: "edge"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Repeat deletion of a still-addressable soft-deleted work identifier."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::task-record"
  - text: "The Task deletion path can return success again and repeat its deletion hooks; exactly-once deletion is not promised."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task"
        effect: "removes"
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

# Accessible repeated soft deletion

## Trigger

Repeat deletion of a still-addressable soft-deleted work identifier.

## Outcome

The Task deletion path can return success again and repeat its deletion hooks; exactly-once deletion is not promised.
