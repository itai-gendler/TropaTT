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

# Organization invitation

Organization/email/proposed admin-or-member Role/inviter/expiry/acceptance/revocation; Pending/Accepted/Revoked.

## Information kept

- **Email** — New invitee email.
- **Role** — Proposed admin or member designation.
- **Inviter** — Inviting person.
- **Expires at** — Acceptance deadline.
- **Accepted at** — Acceptance time.
- **Revoked at** — Revocation time.

## States

### Pending

The invitation has neither been accepted nor revoked; its expiry separately determines whether acceptance remains possible.

### Accepted

The invitation has been marked accepted after Account creation and the attempted membership insertion.

### Revoked

The invitation has been explicitly revoked and cannot be accepted.
