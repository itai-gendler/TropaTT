---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Remove a person from the attendee input of a readable event."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "The Event attendance entry is removed by attendee synchronization."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "event-attendance"
        effect: "removes"
    contexts:
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

# Remove event attendee: successful operation

## Trigger

Remove a person from the attendee input of a readable event.

## Outcome

The Event attendance entry is removed by attendee synchronization.
