---
kind: "primary"
routes:
  web-administration: "Web Administration"
  rest-administration: "Rest Administration"
steps:
  - text: "Supply the addressed record and supported changed metadata."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::roles"
      rest-administration:
        place: "rest::administration"
  - text: "The Role metadata is updated."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "role"
        effect: "changes"
        facts:
          - "Code"
          - "Title"
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

# Edit role: successful operation

## Trigger

Supply the addressed role and supported changed metadata.

## Outcome

The Role metadata is updated.
