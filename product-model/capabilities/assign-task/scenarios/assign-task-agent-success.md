---
kind: "primary"
routes:
  agent: "Agent"
steps:
  - text: "Select an eligible person for assignment. Use only the named tool's advertised arguments."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "The Task assignee changes to the selected person. The inspected MCP output omits secret and financial fields."
    kind: "product"
    actor: "ai-agent"
    entities:
      - entity: "task"
        effect: "changes"
        facts:
          - "Assignee"
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

# Assign task through the connected agent

## Trigger

Select an eligible person for assignment. Use only the named tool's advertised arguments.

## Outcome

The Task assignee changes to the selected person. The inspected MCP output omits secret and financial fields.
