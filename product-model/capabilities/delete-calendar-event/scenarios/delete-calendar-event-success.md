---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select an owned event for deletion."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::calendar"
      rest-work:
        place: "rest::work"
  - text: "The Calendar event record is removed and cancellation recipient messages are produced."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "calendar-event"
        effect: "removes"
      - entity: "event-attendance"
        effect: "removes"
        with: "calendar-event"
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

# Delete calendar event: successful operation

## Trigger

Select an owned event for deletion.

## Outcome

The Calendar event record is removed and cancellation notifications are produced.
