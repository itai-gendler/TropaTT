---
appliesTo:
  - type: "capability"
    id: "create-organization-invitation"
  - type: "capability"
    id: "resend-organization-invitation"
  - type: "capability"
    id: "revoke-organization-invitation"
  - type: "capability"
    id: "accept-organization-invitation"
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

# Invitation acceptance retains expiry and insertion qualifications

Invitations accept only their implemented administrator/member choices and a new eligible email. Requested lifetime is bounded to 1–30 days with seven as the default; resend replaces the token with a fresh seven-day expiry. Accepted/revoked/expired invitations cannot be accepted as pending. Acceptance creates the Account, conditionally assigns the default user Role, attempts membership insertion and marks the invitation accepted; that insertion's result is unchecked. No invitation-delivery guarantee follows from these writes.
