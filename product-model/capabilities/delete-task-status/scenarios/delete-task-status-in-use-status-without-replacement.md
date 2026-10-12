---
kind: "validation"
routes:
  web-administration: "Web Administration"
  rest-work: "Rest Work"
steps:
  - text: "Delete a record-scope status still in use without supplying a replacement."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::task-statuses"
      rest-work:
        place: "rest::work"
  - text: "In-use deletion is refused and the dictionary entry remains."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::task-statuses"
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

# In-use status without replacement

## Trigger

Delete a task-scope status still in use without supplying a replacement.

## Outcome

In-use deletion is refused and the dictionary entry remains.
