---
kind: "primary"
routes:
  agent: "Agent"
steps:
  - text: "Supply nonempty comment text and supported visibility. Use only the named tool's advertised arguments."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "A sanitized Task comment is saved. The inspected MCP output omits secret and financial fields."
    kind: "product"
    actor: "ai-agent"
    entities:
      - entity: "task-comment"
        effect: "creates"
        facts:
          - "Body"
          - "Visibility"
          - "Author"
          - "Created at"
          - "Edited at"
    contexts:
      agent:
        place: "mcp"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/CommentService.php"
---

# Add task comment through the connected agent

## Trigger

Supply nonempty comment text and supported visibility. Use only the named tool's advertised arguments.

## Outcome

A sanitized Task comment is saved. The inspected MCP output omits secret and financial fields.
