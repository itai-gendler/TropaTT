---
appliesTo:
  - type: "capability"
    id: "browse-knowledge"
  - type: "capability"
    id: "browse-page-permissions"
  - type: "capability"
    id: "add-page-permission"
  - type: "capability"
    id: "remove-page-permission"
  - type: "capability"
    id: "browse-space-permissions"
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

# Knowledge visibility is authenticated ranked access

Knowledge public visibility is authenticated ranked access, not anonymous publishing. View/comment/edit/manage ranks, Account/Role/Team/Department subjects, owners and actual Root/raw wildcard/knowledge.admin ACL bypasses are evaluated independently of route codes and workspace/trash filters. ACL-entry administration uses its owner/administrative path rather than mere readable access.
