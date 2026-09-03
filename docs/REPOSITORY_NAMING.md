# Repository Naming Standard

Craniumtek Solutions Inc. uses durable repository names that reflect ownership and purpose without encoding temporary implementation details.

## General rules

- Prefer lowercase names with hyphens.
- Use a product or platform name when one repository owns the product lifecycle.
- Avoid personal names, temporary branch concepts, dates, environment names, and technology names unless the technology is the actual product boundary.
- Do not create one repository per microservice by default. Split only when independent ownership, release cadence, security boundary, or operational lifecycle clearly justifies it.
- New repositories should normally use `main` as the default branch.

## Repository classes

| Class | Example | Purpose |
| --- | --- | --- |
| Organization community | `.github` | Public profile and default community health files |
| Corporate web | `craniumtek-web` | Public corporate application |
| Shared platform | `cranium-platform` | Reusable identity, contracts, and platform primitives |
| AI foundation | `cranium-ai` | Shared AI and agentic capabilities |
| Infrastructure | `cranium-infrastructure` | Infrastructure-as-code and deployment definitions; private by default |
| Operations | `cranium-ops` | Internal source of truth, runbooks, migration plans, and inventories; private |
| Venture | `raketnow`, `ibayong`, `ibahaykubo` | Product/business lifecycle |
| Frontier R&D | `cranium-frontier` | Early deep-tech research monorepo; private by default |
| Archive | existing historical name | Read-only historical repository when retention is useful |

## Product monorepos

For a venture that has multiple apps and services, prefer a product monorepo initially, for example:

```text
raketnow/
├── apps/
├── services/
├── packages/
├── infrastructure/
├── tests/
└── docs/
```

A service may later be extracted when it has a real independent lifecycle.

## Frontier projects

Early research programs such as robotics, manufacturing, drones, electronics, aerospace, and space should begin under `cranium-frontier` rather than creating many empty repositories. Extract a dedicated repository only after the program has substantial code, independent ownership, security requirements, or release needs.

## Visibility

- Production applications, AI systems, infrastructure, operations, and frontier research are private by default.
- Public repositories must have an explicit public purpose: organization profile, open-source project, standards, documentation, or curated technical showcase.
- Public visibility must never be used for secrets, customer data, internal server details, or private business strategy.
