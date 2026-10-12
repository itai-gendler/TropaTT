---
kind: "validation"
routes:
  agent: "Agent"
steps:
  - text: "Malformed release context is rejected."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "Malformed release context is rejected."
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

# Release task lease: refused or unavailable operation

## Trigger

Malformed release context is rejected.

## Outcome

Malformed release context is rejected.
