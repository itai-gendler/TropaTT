---
domain: "tasks"
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

# Task lease

Task/person/agent/run/generation/heartbeat/expiry; active validity is calculated, not a promised expiry operation.

## Information kept

- **Person** — Connected person holding the lease.
- **Agent** — Agent identity.
- **Run** — Run identity.
- **Generation** — Fencing generation.
- **Heartbeat** — Last heartbeat time.
- **Expires at** — Validity deadline.
- **Released at** — Release time.
