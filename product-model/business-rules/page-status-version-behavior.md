---
appliesTo:
  - type: "capability"
    id: "create-knowledge-page"
  - type: "capability"
    id: "edit-knowledge-page"
  - type: "capability"
    id: "publish-knowledge-page"
  - type: "capability"
    id: "archive-knowledge-page"
  - type: "capability"
    id: "restore-knowledge-page"
  - type: "capability"
    id: "request-page-review"
  - type: "capability"
    id: "approve-page-review"
  - type: "capability"
    id: "reject-page-review"
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

# Page states and versions follow the actual entry point

Page creation recognizes the implemented five states. Ordinary editing recognizes Draft, Review, Published and Archived; an unrecognized Needs update input falls back to Draft. REST editing can directly choose Published without completing the explicit review flow. Version writes accompany their actual source operations. A positive supplied page revision is a preliminary check, not the transactional Task fence.
