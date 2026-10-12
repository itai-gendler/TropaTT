---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "A readable event's nonowner supplies changed attendee input."
    kind: "actor"
    actor: "user"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "Event attendance changes through synchronization even when the owner-filtered ordinary event update affects no record."
    kind: "product"
    actor: "user"
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

# Readable nonowner

## Trigger

A readable event's nonowner supplies changed attendee input.

## Outcome

Event attendance changes through synchronization even when the owner-filtered ordinary event update affects no record.
