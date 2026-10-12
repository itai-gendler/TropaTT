---
domain: "organizations"
relations:
  - entity: "organization-membership"
    verb: "has-members"
    cardinality: "one-to-many"
  - entity: "organization-invitation"
    verb: "invites"
    cardinality: "one-to-many"
  - entity: "project"
    verb: "contains-projects"
    cardinality: "one-to-many"
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

# Organization

Title/slug/creation facts; memberships and invitations.

## Information kept

- **Title** — Workspace name.
- **Slug** — Workspace slug resolved with collision handling.
- **Created at** — Workspace creation time.
