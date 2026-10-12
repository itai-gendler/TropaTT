---
kind: "primary"
routes:
  web-administration: "Web Administration"
  rest-administration: "Rest Administration"
steps:
  - text: "Select an existing person-record assignment to remove."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::users"
      rest-administration:
        place: "rest::administration"
  - text: "The User role assignment is removed."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "user-role-assignment"
        effect: "removes"
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

# Remove user role: successful operation

## Trigger

Select an existing person-role assignment to remove.

## Outcome

The User role assignment is removed.
