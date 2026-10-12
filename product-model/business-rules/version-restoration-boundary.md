---
appliesTo:
  - type: "capability"
    id: "restore-page-version"
    contexts:
      - place: "web::work"
      - place: "rest::work"
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

# Version restoration retains its locked-response qualification

Version restoration restores title/content, checks the version belongs to the page, and creates a fresh provenance version rather than rewriting the historical version. The service can return KNOWLEDGE_PAGE_LOCKED, but the controller does not handle that string as its normal failure and can wrap it as truthy success; the mapped outcome does not promise a normal REST refusal envelope for that locked path.
