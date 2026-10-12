---
entities:
  - entity: "calendar-event"
    shows:
      - "Title"
      - "Description"
      - "Owner"
      - "Starts at"
      - "Ends at"
      - "Work"
      - "Source"
      - "Privacy"
  - entity: "event-attendance"
    shows:
      - "Account"
      - "Designation"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/config/routes.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/br1.js"
---

# Calendar

Readable events, normalized times, linked work and attendance.
