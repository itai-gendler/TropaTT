---
kind: "primary"
routes:
  agent: "Agent"
steps:
  - text: "Choose a supported destination status or record through dedicated movement. Use only the named tool's advertised arguments."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "The Task moves to the requested destination and the movement response is returned. The inspected MCP output omits secret and financial fields."
    kind: "product"
    actor: "ai-agent"
    entities:
      - entity: "task"
        effect: "changes"
        facts:
          - "Status"
          - "Project"
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

# Move task through the connected agent

## Trigger

Choose a supported destination status or project through dedicated movement. Use only the named tool's advertised arguments.

## Outcome

The Task moves to the requested destination and the movement response is returned. The inspected MCP output omits secret and financial fields.
