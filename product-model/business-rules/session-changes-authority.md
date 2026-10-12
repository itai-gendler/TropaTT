---
appliesTo:
  - type: "entity"
    id: "session"
    effect: "changes"
permits:
  - configuredBy: "role-permission"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/AuthzService.php#permissionsForUser"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/auth/AuthController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/security/ProfileController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/security/SessionController.php"
---

# Only people authorized for the requested operation change session records

The applicable person is resolved from the authenticated Account; an AI agent is resolved through the person who connects it. Role permission configuration supplies that person's runtime permission codes. Operation dispatch below chooses the required codes and preserves independent route, object, workspace, ownership and external-persona checks as AND conditions. Alternative grants within the stated check are OR. Effective Root bypasses only the named checks; API-client and API-key narrowing applies independently and removes effective Root when scoped. No stored permission entry by itself grants access to a foreign object.

## Operation dispatch

- Sign out, Revoke session: owner internal/executor or applicable Root individual grant; observer write block retained.
- Revoke other sessions: own Account, including explicitly allowed observer REST write.

Sign out addresses the current Session; observers are blocked by the inspected write gate. Individual REST Revoke session allows its internal/executor owner or applicable effective Root branch, never observer writes. Revoke other sessions addresses the current Account and explicitly permits the observer REST self-service write while retaining the current Session. Own-password replacement and conditional public recovery revoke the addressed Account's sessions. Contact/Counterparty external-revocation paths revoke only the sessions of their actually linked external Account after their own authorized parent operation. No separate Role-code permission is required for session self-service.

For authenticated route checks, effective Root grants the implemented bypass; otherwise hasAnyPermissions compares the dispatched required codes literally against AuthzService's trimmed/deduplicated codes. A list containing '*' normalizes to ['*'], but is not by itself an additional route Root bypass. A restricted empty explicit list denies without falling back to Account Role permissions. Object ACL checks that inspect raw codes keep their own wildcard behavior. Public token/credential operations and authenticated operations with no route code retain the explicitly stated no-code path; this delegation does not invent a Role-code requirement for them.

