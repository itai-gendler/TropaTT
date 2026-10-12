---
kind: "edge"
routes:
  web-administration: "Web Administration"
  rest-administration: "Rest Administration"
steps:
  - text: "A nonroot record submits person-record or direct Root-flag input."
    kind: "actor"
    actor: "administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::users"
      rest-administration:
        place: "rest::administration"
  - text: "The record and direct Root input is discarded; no requested assignment is created."
    kind: "condition"
    actor: "administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::users"
      rest-administration:
        place: "rest::administration"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/RoleService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/PermissionService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/user/UserController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/UserService.php"
---

# Nonroot role input

## Trigger

A nonroot administrator submits person-role or direct Root-flag input.

## Outcome

The role and direct Root input is discarded; no requested assignment is created.
