---
appliesTo:
  - type: "entity"
    id: "knowledge-page"
    effect: "changes"
permits:
  - configuredBy: "role-permission"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/AuthzService.php#permissionsForUser"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/knowledge/KnowledgeController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/knowledge/KnowledgeRepository.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/KnowledgePageVersionService.php"
---

# Only people authorized for the requested operation change knowledge page records

The applicable person is resolved from the authenticated Account; an AI agent is resolved through the person who connects it. Role permission configuration supplies that person's runtime permission codes. Operation dispatch below chooses the required codes and preserves independent route, object, workspace, ownership and external-persona checks as AND conditions. Alternative grants within the stated check are OR. Effective Root bypasses only the named checks; API-client and API-key narrowing applies independently and removes effective Root when scoped. No stored permission entry by itself grants access to a foreign object.

## Operation dispatch

- Edit knowledge page, Restore knowledge page, Request page review: knowledge.edit AND edit-ranked access.
- Publish knowledge page, Approve page review, Reject page review: knowledge.publish AND edit-ranked access.
- Archive knowledge page: knowledge.delete AND edit-ranked access.
- Restore page version: knowledge.publish AND edit-ranked access.

updatePage (Edit knowledge page), restorePage (Restore knowledge page) and requestReview require knowledge.edit AND edit-ranked page access. Explicit publish, approve/reject review and restoreVersion require knowledge.publish AND edit-ranked page access. archivePage requires knowledge.delete AND edit-ranked page access. Logical deletion's metadata effects use knowledge.delete AND manage-ranked access. Ordinary editing may set Published directly and may send Needs update to Draft; this does not add the explicit publish code to updatePage. Role/wildcard/effective Root/knowledge.admin ACL bypass is evaluated separately from the applicable route code, so knowledge.admin alone does not replace a missing route permission.

For authenticated route checks, effective Root grants the implemented bypass; otherwise hasAnyPermissions compares the dispatched required codes literally against AuthzService's trimmed/deduplicated codes. A list containing '*' normalizes to ['*'], but is not by itself an additional route Root bypass. A restricted empty explicit list denies without falling back to Account Role permissions. Object ACL checks that inspect raw codes keep their own wildcard behavior. Public token/credential operations and authenticated operations with no route code retain the explicitly stated no-code path; this delegation does not invent a Role-code requirement for them.

