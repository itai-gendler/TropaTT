---
domain: "projects"
relations:
  - entity: "task"
    verb: "contains-work"
    cardinality: "one-to-many"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/project/ProjectController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ProjectService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/project/ProjectRepository.php"
---

# Project

Title/description/status/priority/dates/prefix/revision/archive; customer, manager, team, creator and Tasks.

## Information kept

- **Title** — Project name.
- **Description** — Work description.
- **Status** — Current project status.
- **Priority** — Project priority.
- **Start date** — Planned start.
- **Due date** — Planned finish.
- **Prefix** — Unique project task-key prefix.
- **Revision** — Supplied revision used for preliminary conflict checks.
- **Archived at** — Archival date.
- **Creator** — Creating person.
- **Manager** — Assigned manager.
- **Team** — Assigned team.
- **Counterparty** — Linked customer or business context.
