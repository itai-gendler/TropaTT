---
kind: "primary"
routes:
  agent: "Agent"
steps:
  - text: "Choose an accepted status for ordinary or selected bulk updating. Use only the named tool's advertised arguments."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "The kept status code changes; bulk requests report per-item results. The inspected MCP output omits secret and financial fields."
    kind: "product"
    actor: "ai-agent"
    entities:
      - entity: "task"
        effect: "changes"
        facts:
          - "Status"
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

# Change task status through the connected agent

## Trigger

Choose an accepted status for ordinary or selected bulk updating. Use only the named tool's advertised arguments.

## Outcome

The Task status changes; bulk requests report per-item results. The inspected MCP output omits secret and financial fields.
