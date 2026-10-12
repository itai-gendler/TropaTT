---
entities:
  - entity: "knowledge-page"
    shows:
      - "Title"
      - "Content"
      - "Type"
      - "Parent"
      - "Owner"
      - "Client visible"
      - "Revision"
      - "Review"
      - "Publication"
      - "Deleted at"
  - entity: "knowledge-version"
    shows:
      - "Title"
      - "Content"
      - "Number"
      - "Author"
      - "Created at"
      - "Change summary"
      - "Restoration provenance"
  - entity: "page-permission"
    shows:
      - "Subject"
      - "Access level"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Knowledge page

Selected saved page, content, status outcome, revision, versions and configured page access entries.
