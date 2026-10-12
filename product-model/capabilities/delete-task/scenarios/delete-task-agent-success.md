---
kind: "primary"
routes:
  agent: "Agent"
steps:
  - text: "Confirm deletion of the selected work. Use only the named tool's advertised arguments."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "The Task is soft-deleted and direct child work is cascaded by the inspected deletion path. The inspected MCP output omits secret and financial fields."
    kind: "product"
    actor: "ai-agent"
    entities:
      - entity: "task"
        effect: "removes"
      - entity: "subtask"
        effect: "removes"
        with: "task"
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

# Delete task through the connected agent

## Trigger

Confirm deletion of the selected work. Use only the named tool's advertised arguments.

## Outcome

The Task is soft-deleted and direct child work is cascaded by the inspected deletion path. The inspected MCP output omits secret and financial fields.
