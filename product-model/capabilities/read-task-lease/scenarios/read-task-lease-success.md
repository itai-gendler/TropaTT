---
kind: "primary"
routes:
  agent: "Agent"
steps:
  - text: "Request the selected work's lease information."
    kind: "actor"
    actor: "ai-agent"
    entities: []
    contexts:
      agent:
        place: "mcp"
  - text: "Task lease validity information is returned; expired records are not reported as active."
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

# Read task lease: successful operation

## Trigger

Request the selected work's lease information.

## Outcome

Task lease validity information is returned; expired records are not reported as active.
