---
appliesTo:
  - type: "capability"
    id: "browse-task-comments"
  - type: "capability"
    id: "add-task-comment"
  - type: "capability"
    id: "edit-task-comment"
  - type: "capability"
    id: "delete-task-comment"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/CommentService.php"
---

# Comments retain sanitized input and external visibility

Task comments sanitize and bound the accepted body and require applicable work scope. External creation/listing forces the supported client-visible path; an external input cannot make an internal-only comment visible by bypassing the implemented filter. Edit/delete ownership and participation grants are separate permission Rules.
