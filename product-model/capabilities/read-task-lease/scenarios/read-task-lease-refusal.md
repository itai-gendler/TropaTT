---
kind: "validation"
routes:
  agent: "Agent"
steps:
  - text: "Invalid work or record context prevents a valid lease read."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "Invalid work or record context prevents a valid lease read."
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

# Read task lease: refused or unavailable operation

## Trigger

Invalid work or organization context prevents a valid lease read.

## Outcome

Invalid work or organization context prevents a valid lease read.
