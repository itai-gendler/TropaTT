---
domain: "knowledge"
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
---

# Knowledge version

Addressed saved title/content/version/author/date/change summary/restoration provenance.

## Information kept

- **Title** — Saved page title.
- **Content** — Saved page content.
- **Number** — Addressed version number.
- **Author** — Saving person.
- **Created at** — Save time.
- **Change summary** — Change note.
- **Restoration provenance** — Source version information for restored snapshots.
