---
appliesTo:
  - type: "capability"
    id: "sign-out"
  - type: "capability"
    id: "browse-sessions"
  - type: "capability"
    id: "revoke-session"
  - type: "capability"
    id: "revoke-other-sessions"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/auth/AuthController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/security/ProfileController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/security/SessionController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/AuthService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/UserProfileService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/SessionService.php"
---

# Only active unexpired sessions authenticate

A session authenticates only while its Account is active, it has not expired and it is not revoked. Individual revocation addresses the current person's session and repeated revocation can report not found rather than promising a new state change. Other-session revocation excludes the current session.
