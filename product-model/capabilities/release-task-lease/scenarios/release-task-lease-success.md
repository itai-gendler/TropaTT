---
kind: "primary"
routes:
  agent: "Agent"
steps:
  - text: "Supply the exact current lease context for release."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "The Task lease is released."
    kind: "product"
    actor: "ai-agent"
    entities:
      - entity: "task-lease"
        effect: "changes"
        facts:
          - "Released at"
    contexts:
      agent:
        place: "mcp"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/mcp/McpController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/AgentLeaseService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/config/mcp_permissions.php"
---

# Release task lease: successful operation

## Trigger

Supply the exact current lease context for release.

## Outcome

The Task lease is released.
