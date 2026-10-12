---
kind: "primary"
routes:
  web-administration: "Web Administration"
  rest-administration: "Rest Administration"
steps:
  - text: "Select a runtime record and a valid permission code to add."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::roles"
      rest-administration:
        place: "rest::administration"
  - text: "The access classification permission entry is kept for that access classification."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "role-permission"
        effect: "creates"
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

# Add role permission: successful operation

## Trigger

Select a runtime role and a valid permission code to add.

## Outcome

The Role permission entry is kept for that role.
