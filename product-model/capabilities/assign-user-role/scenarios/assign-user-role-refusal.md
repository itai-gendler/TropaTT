---
kind: "validation"
routes:
  web-administration: "Web Administration"
  rest-administration: "Rest Administration"
steps:
  - text: "An unavailable target person cannot receive the assignment."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::users"
      rest-administration:
        place: "rest::administration"
  - text: "An unavailable target person cannot receive the assignment."
    kind: "condition"
    actor: "root-administrator"
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

# Assign user role: refused or unavailable operation

## Trigger

An unavailable target person cannot receive the assignment.

## Outcome

An unavailable target person cannot receive the assignment.
