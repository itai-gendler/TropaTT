---
kind: "primary"
routes:
  web-administration: "Web Administration"
  rest-administration: "Rest Administration"
steps:
  - text: "Select a removable unassigned runtime record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::roles"
      rest-administration:
        place: "rest::administration"
  - text: "The addressed Role is removed."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "role"
        effect: "removes"
    contexts:
      web-administration:
        place: "web::administration::roles"
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

# Delete role: successful operation

## Trigger

Select a removable unassigned runtime role.

## Outcome

The addressed Role is removed.
