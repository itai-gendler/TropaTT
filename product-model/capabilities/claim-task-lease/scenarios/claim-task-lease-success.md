---
kind: "primary"
routes:
  agent: "Agent"
steps:
  - text: "Supply a fresh run identity and valid lease token with a supported TTL."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "A Task lease is claimed with generation, heartbeat and expiry information."
    kind: "product"
    actor: "ai-agent"
    entities:
      - entity: "task-lease"
        effect: "creates"
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

# Claim task lease: successful operation

## Trigger

Supply a fresh run identity and valid lease token with a supported TTL.

## Outcome

A Task lease is claimed with generation, heartbeat and expiry information.
