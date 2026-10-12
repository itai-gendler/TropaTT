---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Request the record dictionary through the executor-enabled list endpoint."
    kind: "actor"
    actor: "external-executor"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "The request returns activity codes instead of the requested status dictionary rows."
    kind: "condition"
    actor: "external-executor"
    entities: []
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

# Browse task statuses as external executor

## Trigger

Request the task dictionary through the executor-enabled list endpoint.

## Outcome

The request is forced to worklog_activity; activity codes are returned and task-scope dictionary rows are not disclosed.
