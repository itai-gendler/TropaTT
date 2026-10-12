---
domain: "tasks"
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
---

# Task activity

Displayed actor/event/field/prior/new value/time.

## Information kept

- **Actor** — Person attributed to the event.
- **Event** — Recorded work event.
- **Field** — Changed field when present.
- **Previous value** — Recorded prior value.
- **New value** — Recorded resulting value.
- **Created at** — Event time.
