---
kind: "edge"
routes:
  agent: "Agent"
steps:
  - text: "Renew after token/run/generation or ownership no longer matches."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "Renewal fails without advancing the heartbeat or expiry."
    kind: "condition"
    actor: "ai-agent"
    entities: []
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

# Renewal ownership/context lost

## Trigger

Renew after token/run/generation or ownership no longer matches.

## Outcome

Renewal fails without advancing the heartbeat or expiry.
