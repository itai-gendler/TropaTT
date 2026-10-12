---
appliesTo:
  - type: "entity"
    id: "knowledge-version"
    effect: "creates"
permits:
  - configuredBy: "role-permission"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/knowledge/KnowledgeController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/knowledge/KnowledgeRepository.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/KnowledgePageVersionService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/knowledge/KnowledgePageVersionController.php"
---

# Only the authorized source operation changes knowledge version records

Version creation inherits the exact authorized parent page operation: createPage uses knowledge.create with editable destination; updatePage uses knowledge.edit with edit-ranked access; explicit publish/approve and restoreVersion use knowledge.publish with edit-ranked access. The resulting version is not an independently invocable creation ability. Title/content snapshots, authors and restoration provenance are kept under those source operations.

For authenticated route checks, effective Root grants the implemented bypass; otherwise hasAnyPermissions compares the dispatched required codes literally against AuthzService's trimmed/deduplicated codes. A list containing '*' normalizes to ['*'], but is not by itself an additional route Root bypass. A restricted empty explicit list denies without falling back to Account Role permissions. Object ACL checks that inspect raw codes keep their own wildcard behavior. Public token/credential operations and authenticated operations with no route code retain the explicitly stated no-code path; this delegation does not invent a Role-code requirement for them.

