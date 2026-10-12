---
domain: "companies"
relations:
  - entity: "counterparty"
    verb: "shares-record"
    cardinality: "one-to-one"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ClientService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/CompanyService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/CounterpartyService.php"
---

# Company

Addressed organization-kind title/status/email/tax-number contract.

## Information kept

- **Title** — Addressed organization title.
- **Status** — Current company designation.
- **Email** — Company contact email.
- **Tax number** — Company tax identifier.
