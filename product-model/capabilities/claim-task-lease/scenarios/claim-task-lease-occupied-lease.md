---
kind: "edge"
routes:
  agent: "Agent"
steps:
  - text: "Claim work already held by another active lease."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "The occupied lease claim is refused."
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

# Occupied lease

## Trigger

Claim work already held by another active lease.

## Outcome

The occupied lease claim is refused.
