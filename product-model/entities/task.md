---
domain: "tasks"
relations:
  - entity: "task"
    verb: "parents-work"
    cardinality: "one-to-many"
  - entity: "subtask"
    verb: "has-subtasks"
    cardinality: "one-to-many"
  - entity: "checklist"
    verb: "has-checklists"
    cardinality: "one-to-many"
  - entity: "task-comment"
    verb: "has-comments"
    cardinality: "one-to-many"
  - entity: "task-attachment"
    verb: "has-attachments"
    cardinality: "one-to-many"
  - entity: "task-tag-assignment"
    verb: "has-tags"
    cardinality: "one-to-many"
  - entity: "task-activity"
    verb: "has-activity"
    cardinality: "one-to-many"
  - entity: "task-lease"
    verb: "has-leases"
    cardinality: "one-to-many"
  - entity: "worklog"
    verb: "has-time"
    cardinality: "one-to-many"
  - entity: "task-relation"
    verb: "has-outgoing-relations"
    cardinality: "one-to-many"
  - entity: "task-relation"
    verb: "has-incoming-relations"
    cardinality: "one-to-many"
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

# Task

Key/title/description/status/priority/activity/dates/revision/archive/deletion/rate overrides; creator, assignee, Project/customer/parent.

## Information kept

- **Key** — Stable generated work key.
- **Title** — Work title.
- **Description** — Work description.
- **Status** — Kept status code, without an assumed unique dictionary row.
- **Priority** — Work priority.
- **Activity** — Activity classification.
- **Start date** — Planned start.
- **Due date** — Planned due date.
- **Revision** — Revision used by the ordinary positive-version write fence.
- **Archived at** — Archival date distinct from deletion.
- **Deleted at** — Soft-deletion date.
- **Creator** — Creating person.
- **Assignee** — Assigned person or empty assignment.
- **Project** — Project placement.
- **Counterparty** — Customer context.
- **Parent** — Optional parent work.
- **Cost rate** — Explicit task cost override.
- **Bill rate** — Explicit task billing override.
- **Payout rate** — Explicit task payout override.
- **Currency** — Financial currency.
