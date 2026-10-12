---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a title, valid start/finish, source and supported linked work."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::calendar"
      rest-work:
        place: "rest::work"
  - text: "A Calendar event is saved with its owner and normalized UTC times."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "calendar-event"
        effect: "creates"
        facts:
          - "Title"
          - "Description"
          - "Owner"
          - "Starts at"
          - "Ends at"
          - "Work"
          - "Source"
          - "Privacy"
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

# Create calendar event: successful operation

## Trigger

Supply a title, valid start/finish, source and supported linked work.

## Outcome

A Calendar event is saved with its owner and normalized UTC times.
