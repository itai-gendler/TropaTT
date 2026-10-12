---
domain: "task-statuses"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/status/StatusController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/StatusService.php"
---

# Task status

Task-scope code/title/order/active/terminal/WIP information; runtime dictionary instances.

## Information kept

- **Code** — Runtime task-scope status code.
- **Title** — Displayed status title.
- **Order** — Dictionary ordering.
- **Active** — Availability designation.
- **Terminal** — Closed-status dictionary flag.
- **WIP limit** — Dedicated movement column limit.
- **Organization** — Dictionary workspace context.
