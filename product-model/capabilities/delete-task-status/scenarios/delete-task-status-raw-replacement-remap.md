---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Delete an in-use record-scope status with a valid replacement code."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "Task Status is remapped through the raw repository path before Task status removal; normal revision/fence/history behavior is not implied."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task"
        effect: "changes"
        facts:
          - "Status"
      - entity: "task-status"
        effect: "removes"
    contexts:
      rest-work:
        place: "rest::work"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/status/StatusController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/StatusService.php"
---

# Raw replacement/remap

## Trigger

Delete an in-use task-scope status with a valid replacement code.

## Outcome

Task Status is remapped through the raw repository path before Task status removal; normal revision/fence/history behavior is not implied.
