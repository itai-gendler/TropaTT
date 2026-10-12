---
kind: "primary"
routes:
  agent: "Agent"
steps:
  - text: "Use the advertised agent movement input with only a record destination."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "Task work container and Revision change while the existing status is preserved."
    kind: "product"
    actor: "ai-agent"
    entities:
      - entity: "task"
        effect: "changes"
        facts:
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

# Project-only MCP movement

## Trigger

Use the advertised agent movement input with only a project destination.

## Outcome

Task Project and Revision change while the existing status is preserved.
