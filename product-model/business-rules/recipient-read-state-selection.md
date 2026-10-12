---
appliesTo:
  - type: "capability"
    id: "browse-notifications"
  - type: "capability"
    id: "create-notification"
  - type: "capability"
    id: "mark-notification-read"
  - type: "capability"
    id: "mark-notification-unread"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/NotificationService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/notification/NotificationController.php"
---

# Notifications retain recipient and organization-input selection

Notification reads/read-state updates select the actual recipient. Manual creation's Root override and organization input retain their implemented qualifications; these paths do not establish universal tenant isolation or arbitrary nonroot recipient access.
