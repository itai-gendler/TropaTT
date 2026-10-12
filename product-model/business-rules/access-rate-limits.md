---
appliesTo:
  - type: "capability"
    id: "sign-in"
  - type: "capability"
    id: "reset-password"
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

# Access attempts retain their configured rate limits

Login and reset-request attempts use the inspected rate-limit buckets and configured thresholds; exceeding a bucket refuses that attempt without completing authentication or recovery. This is independent of credential validity.
