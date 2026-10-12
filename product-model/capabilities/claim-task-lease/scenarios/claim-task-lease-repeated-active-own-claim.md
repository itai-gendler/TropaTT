---
kind: "edge"
routes:
  agent: "Agent"
steps:
  - text: "Claim the current active lease again using the same owning agent/run context."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "The Task lease is returned with its existing expiry and generation; repeated claim does not renew it."
    kind: "product"
    actor: "ai-agent"
    entities:
      - entity: "task-lease"
        effect: "reads"
        facts:
          - "Person"
          - "Agent"
          - "Run"
          - "Generation"
          - "Heartbeat"
          - "Expires at"
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

# Repeated active own claim

## Trigger

Claim the current active lease again using the same owning agent/run context.

## Outcome

The Task lease is returned with its existing expiry and generation; repeated claim does not renew it.
