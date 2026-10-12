---
appliesTo:
  - type: "capability"
    id: "restore-knowledge-space"
  - type: "capability"
    id: "delete-knowledge-space"
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

# Space trash and restoration retain subtree rules

Space trash hides its subtree and contained pages. Restoration retains child handling and detaches a restored child when its parent remains deleted. Protected/system spaces keep their guards. Space restoration does not imply publication or permanent deletion of descendant pages.
