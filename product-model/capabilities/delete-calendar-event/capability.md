---
availability:
  - place: "web::work"
  - place: "rest::work"
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
domain: "calendar"
---

# Delete calendar event

The Calendar event record is removed and cancellation notifications are produced.
