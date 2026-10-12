---
kind: "primary"
routes:
  agent: "Agent"
steps:
  - text: "Supply supported ordinary metadata and, optionally, a positive current revision. Use only the named tool's advertised arguments."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "The Task metadata is saved through the ordinary write fence and its revision advances. The inspected MCP output omits secret and financial fields."
    kind: "product"
    actor: "ai-agent"
    entities:
      - entity: "task"
        effect: "changes"
        facts:
          - "Title"
          - "Description"
          - "Priority"
          - "Activity"
          - "Start date"
          - "Due date"
          - "Project"
          - "Counterparty"
          - "Revision"
    contexts:
      agent:
        place: "mcp"
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

# Edit task through the connected agent

## Trigger

Supply supported ordinary metadata and, optionally, a positive current revision. Use only the named tool's advertised arguments.

## Outcome

The Task metadata is saved through the ordinary write fence and its revision advances. The inspected MCP output omits secret and financial fields.
