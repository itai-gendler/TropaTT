---
domain: "roles"
relations:
  - entity: "api-key"
    verb: "issues"
    cardinality: "one-to-many"
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

# API client

Name/activity, bound configuration and role/permission restrictions.

## Information kept

- **Name** — Integration client title.
- **Active** — Client activity configuration.
- **Scopes** — Stored client permission restrictions.
- **Organization** — Stored workspace binding.
