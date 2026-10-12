---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply supported detail changes for an owned event."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::calendar"
      rest-work:
        place: "rest::work"
  - text: "Calendar event details change; attendance is a separately governed effect."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "calendar-event"
        effect: "changes"
        facts:
          - "Title"
          - "Description"
          - "Starts at"
          - "Ends at"
          - "Work"
    contexts:
      web-work:
        place: "web::work::calendar"
      rest-work:
        place: "rest::work"
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

# Edit calendar event: successful operation

## Trigger

Supply supported detail changes for an owned event.

## Outcome

Calendar event details change; attendance is a separately governed effect.
