---
appliesTo:
  - type: "capability"
    id: "send-chat-message"
  - type: "capability"
    id: "edit-chat-message"
  - type: "capability"
    id: "delete-chat-message"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ChatService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/chat/ChatController.php"
---

# Messages retain exact retry and time-window checks

Messages validate body bounds, reply-to within the same chat and retry identity. Request identity is 16–80 characters; chat, sender and key determine retry lookup, and changed body/reply or a deleted match conflicts instead of silently creating another message. Own edit and removal windows are 60 and 10 minutes respectively; Root does not bypass those time windows.
