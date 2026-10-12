---
kind: "validation"
routes:
  agent: "Agent"
steps:
  - text: "Malformed token, run identity or TTL is rejected."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "Malformed token, run identity or TTL is rejected."
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

# Claim task lease: refused or unavailable operation

## Trigger

Malformed token, run identity or TTL is rejected.

## Outcome

Malformed token, run identity or TTL is rejected.
