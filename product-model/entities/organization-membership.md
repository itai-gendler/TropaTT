---
domain: "organizations"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/OrganizationService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/OrganizationContextService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/InvitationService.php"
---

# Organization membership

Organization, Account, container Role and membership date.

## Information kept

- **Role** — Owner, admin or member designation within this workspace.
- **Joined at** — Membership date.
- **Account** — Member identity.
