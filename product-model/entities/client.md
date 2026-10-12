---
domain: "clients"
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

# Client

Addressed kind/title/personal/legal/tax/bank/contact/address/status/additional facts.

## Information kept

- **Kind** — Individual, sole proprietor or legal entity classification.
- **Title** — Addressed customer title.
- **Person details** — Optional personal-name information.
- **Legal details** — Optional legal and registration information.
- **Tax number** — Tax identifier.
- **Bank details** — Optional banking information.
- **Email** — Contact email.
- **Phone** — Contact telephone.
- **Address** — Optional customer address.
- **Status** — Current customer designation.
- **Additional information** — Optional additional customer information.
