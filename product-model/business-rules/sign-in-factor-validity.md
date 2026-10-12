---
appliesTo:
- type: capability
  id: sign-in
  contexts:
  - place: web::public
  - place: rest::public
references:
- kind: code
  role: implementation
  target: upload/api/system/library/service/AuthService.php#resolveTwoFactorToken
- kind: code
  role: implementation
  target: upload/api/system/library/service/AuthService.php#completeTwoFactorLogin
---

# Sign-in completes only with a valid factor continuation

A pending second-factor sign-in is time-limited. Invalid, expired or replayed continuations do not complete the session; a valid continuation completes the same sign-in ability and issues its active session rather than a separate product ability.
