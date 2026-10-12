---
domain: "counterparties"
relations:
  - entity: "contact"
    verb: "has-contacts"
    cardinality: "one-to-many"
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

# Counterparty

Kind and one common list of optional personal/legal/tax/bank/contact/address/status/additional facts.

## Information kept

- **Kind** — Customer or business classification.
- **Title** — Business record title.
- **Person details** — Optional personal-name information.
- **Legal details** — Optional legal and registration information.
- **Tax number** — Tax identifier.
- **Bank details** — Optional banking information.
- **Email** — Contact email.
- **Phone** — Contact telephone.
- **Address** — Optional business address.
- **Status** — Current designation.
- **Additional information** — Optional additional business information.
