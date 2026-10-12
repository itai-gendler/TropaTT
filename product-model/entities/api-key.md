---
domain: "roles"
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

# API key

Client/Account binding, name, restrictions, expiry/revocation; no secret hashes as Product facts.

## Information kept

- **Name** — Credential designation.
- **Scopes** — Stored key permission restrictions.
- **Expires at** — Optional validity deadline.
- **Revoked at** — Explicit credential revocation.
- **Account** — Bound person.
- **Client** — Bound integration client.
