---
kind: "primary"
routes:
  agent: "Agent"
steps:
  - text: "Read a work collection or a selected work identifier. Use only the named tool's advertised arguments."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "Task facts are returned with filtering appropriate to the response path. The inspected MCP output omits secret and financial fields."
    kind: "product"
    actor: "ai-agent"
    entities:
      - entity: "task"
        effect: "reads"
        facts:
          - "Key"
          - "Title"
          - "Description"
          - "Status"
          - "Priority"
          - "Activity"
          - "Start date"
          - "Due date"
          - "Revision"
          - "Archived at"
          - "Deleted at"
          - "Creator"
          - "Assignee"
          - "Project"
          - "Counterparty"
          - "Parent"
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

# Browse tasks through the connected agent

## Trigger

Read a work collection or a selected work identifier. Use only the named tool's advertised arguments.

## Outcome

Task facts are returned with filtering appropriate to the response path. The inspected MCP output omits secret and financial fields.
