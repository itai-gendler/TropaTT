---
actors:
  - "root-administrator"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/view/template/page/chat.php"
  - kind: "code"
    role: "implementation"
    target: "upload/web/assets/js/page-api-bindings.js"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ChatService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/chat/ChatController.php"
---

# Start a conversation

## Goal

Create a group Chat and enter the conversation the Product selects.

## Success criterion

The newly created Chat is selected and its conversation is read.
