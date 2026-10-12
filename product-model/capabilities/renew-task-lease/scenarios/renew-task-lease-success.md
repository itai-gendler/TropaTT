---
kind: "primary"
routes:
  agent: "Agent"
steps:
  - text: "Supply the exact current token, run and generation for renewal."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "The Task lease heartbeat and expiry advance."
    kind: "product"
    actor: "ai-agent"
    entities:
      - entity: "task-lease"
        effect: "changes"
        facts:
          - "Heartbeat"
          - "Expires at"
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

# Renew task lease: successful operation

## Trigger

Supply the exact current token, run and generation for renewal.

## Outcome

The Task lease heartbeat and expiry advance.
