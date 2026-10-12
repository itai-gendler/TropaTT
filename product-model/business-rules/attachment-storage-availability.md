---
appliesTo:
  - type: "capability"
    id: "upload-task-attachment"
  - type: "capability"
    id: "download-task-attachment"
  - type: "capability"
    id: "remove-task-attachment"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/file/FileController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/FileService.php"
---

# Attachments retain safe storage and actual byte availability

Attachment creation validates its bound object, file type, byte size and storage path. Quarantine and safe streaming checks govern downloads; missing bytes can refuse a download despite a surviving metadata record. Logical removal is not proof that bytes were securely erased or will remain available forever.
