---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
  web-detail: "Web Detail"
  web-my-day: "Web My Day"
  web-my-week: "Web My Week"
  rest-record: "Rest Record"
steps:
  - text: "Unavailable work is absent from the list or returns the work-not-found result."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::tasks"
      rest-work:
        place: "rest::work::task-collection"
      web-detail:
        place: "web::work::task-detail"
      web-my-day:
        place: "web::work::my-day"
      web-my-week:
        place: "web::work::my-week"
      rest-record:
        place: "rest::work::task-record"
  - text: "Unavailable work is absent from the list or returns the work-not-found result."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::tasks"
      rest-work:
        place: "rest::work::task-collection"
      web-detail:
        place: "web::work::task-detail"
      web-my-day:
        place: "web::work::my-day"
      web-my-week:
        place: "web::work::my-week"
      rest-record:
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

# Browse tasks: refused or unavailable operation

## Trigger

Unavailable work is absent from the list or returns TASK_NOT_FOUND.

## Outcome

Unavailable work is absent from the list or returns TASK_NOT_FOUND.
