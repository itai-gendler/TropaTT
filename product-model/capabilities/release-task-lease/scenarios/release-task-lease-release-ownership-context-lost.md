---
kind: "edge"
routes:
  agent: "Agent"
steps:
  - text: "Release after token/run/generation or ownership no longer matches."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "Release fails without successfully releasing the current holder."
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

# Release ownership/context lost

## Trigger

Release after token/run/generation or ownership no longer matches.

## Outcome

Release fails without successfully releasing the current holder.
