---
entities:
  - entity: "knowledge-space"
    shows:
      - "Title"
      - "Description"
      - "Parent"
      - "Owner"
      - "Visibility"
      - "Default access"
      - "Revision"
      - "Archived at"
      - "Deleted at"
      - "System"
  - entity: "knowledge-page"
    shows:
      - "Title"
      - "Type"
      - "Parent"
      - "Owner"
      - "Client visible"
      - "Revision"
      - "Review"
      - "Publication"
      - "Deleted at"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Knowledge

Spaces, hierarchy and selected page summaries within authenticated ranked access.
