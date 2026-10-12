---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Supply a valid person in the attendee input of a readable event."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "Event attendance is added or replaced through the event's attendee synchronization path."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "event-attendance"
        effect: "creates"
        facts:
          - "Account"
          - "Designation"
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

# Add event attendee: successful operation

## Trigger

Supply a valid person in the attendee input of a readable event.

## Outcome

Event attendance is added or replaced through the event's attendee synchronization path.
