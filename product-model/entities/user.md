---
acts: "internal"
kind: "person"
relations:
  - entity: "account"
    verb: "has-identity"
    cardinality: "one-to-one"
  - entity: "ai-agent"
    verb: "connects"
    cardinality: "one-to-many"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/web/install.php"
---

# User

Internal person in the shipped User identity, related to Account.
