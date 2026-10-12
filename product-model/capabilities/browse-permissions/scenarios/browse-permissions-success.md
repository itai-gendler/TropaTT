---
kind: "primary"
routes:
  web-administration: "Web Administration"
  rest-administration: "Rest Administration"
steps:
  - text: "Read the permission entries of the selected runtime record."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::roles"
      rest-administration:
        place: "rest::administration"
  - text: "Role permission codes and their definitions are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "role-permission"
        effect: "reads"
        facts:
          - "Permission code"
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

# Browse permissions: successful operation

## Trigger

Read the permission entries of the selected runtime role.

## Outcome

Role permission codes and their definitions are returned.
