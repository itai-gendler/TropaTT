---
kind: "primary"
routes:
  web-administration: "Web Administration"
  rest-administration: "Rest Administration"
steps:
  - text: "Select an assigned permission code for removal."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::roles"
      rest-administration:
        place: "rest::administration"
  - text: "The access classification permission entry is removed from the selected access classification."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "role-permission"
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

# Remove role permission: successful operation

## Trigger

Select an assigned permission code for removal.

## Outcome

The Role permission entry is removed from the selected role.
