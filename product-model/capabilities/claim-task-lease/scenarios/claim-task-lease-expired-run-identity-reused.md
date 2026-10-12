---
kind: "edge"
routes:
  agent: "Agent"
steps:
  - text: "Claim using an expired run identity where a fresh identity is required."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "Reuse of the expired run identity is refused; a fresh claim is not established."
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

# Expired run identity reused

## Trigger

Claim using an expired run identity where a fresh identity is required.

## Outcome

Reuse of the expired run identity is refused; a fresh claim is not established.
