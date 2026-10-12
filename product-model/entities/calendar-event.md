---
domain: "calendar"
relations:
  - entity: "event-attendance"
    verb: "has-attendees"
    cardinality: "one-to-many"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/calendar/CalendarController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/CalendarService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/calendar/CalendarEventRepository.php"
---

# Calendar event

Title/description/owner/times/linked work/source/privacy; deletion removes it.

## Information kept

- **Title** — Event title.
- **Description** — Event description.
- **Owner** — Owning person.
- **Starts at** — UTC-normalized start.
- **Ends at** — UTC-normalized finish.
- **Work** — Linked task or project.
- **Source** — Event source and source-owner identity.
- **Privacy** — Source privacy designation.
