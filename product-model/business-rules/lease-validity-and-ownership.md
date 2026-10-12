---
appliesTo:
  - type: "capability"
    id: "read-task-lease"
  - type: "capability"
    id: "claim-task-lease"
  - type: "capability"
    id: "renew-task-lease"
  - type: "capability"
    id: "release-task-lease"
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

# Leases retain exact owner token run generation and expiry

Lease claim uses the current assignee identity, caller run and a caller-held token stored as a hash, with generation and a 30–900-second TTL bound. Repeating a matching live claim returns that lease without extending expiry. An occupied live lease refuses another owner; expiry permits the implemented next generation. Renewal and release require the exact token/run/generation and assignee; stale or lost ownership refuses even for Root.
