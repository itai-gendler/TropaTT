---
id: tropatt
summary: Self-hosted CRM and work platform for client projects, work coordination, collaboration, knowledge and recorded time.
category: work-management
tags: [crm, projects, tasks, collaboration, knowledge, time-tracking]
authors:
  - name: Anton Barinov
license: AGPL-3.0
languages: [en-GB, ru-RU, zh-CN]
limitations:
  - Records stay on the operator's own server; TropaTT does not sync them to any cloud.
  - Built-in AI uses provider keys the operator supplies, and its suggestions change records only after a person reviews them.
  - Connected agents act with no more authority than the person they act for.
  - External observers and executors reach only the customer context and Projects they are linked to.
  - A stock installation has no modules; store connectors, migrations and calendar sync are installed separately from the module marketplace.
references:
  - kind: doc
    role: context
    target: README.md
    title: Product identity and creator attribution
  - kind: code
    role: implementation
    target: upload/web/config/routes.php
    title: Browser work-platform subjects
  - kind: code
    role: implementation
    target: upload/api/config/routes.php
    title: Core work-platform interaction contracts
---

# TropaTT

TropaTT is a self-hosted CRM and work platform. People coordinate client projects and tasks, keep customer and contact records, collaborate in conversations and knowledge pages, organize calendar events, record time and resolve incoming work. Rate cards and recorded time support financial calculations. Browser pages, REST contracts and connected agents provide supported ways to interact with the work platform.

## Intent

Keep customer context and the work performed for it together on infrastructure operated by the people using the Product.
