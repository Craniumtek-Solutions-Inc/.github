# Public Engineering Standard

This document summarizes the public-safe engineering principles Craniumtek Solutions Inc. expects across maintained repositories. Repository-specific standards may be stricter.

## Source control

- Git is the source of truth for code and reviewed configuration.
- Production servers are deployment targets, not the origin of development.
- Important production changes should be traceable to an exact reviewed commit or release.
- Direct production editing should be avoided except for documented emergency procedures.

## Change control

- Prefer small, scoped branches and pull requests.
- Explain objective, risk, verification, and rollback or forward-repair strategy.
- Separate unrelated refactors from urgent fixes.
- Protect production-critical branches with appropriate review and status requirements.

## Security

- No credentials or private production data in repositories.
- Apply least privilege to people, tokens, runners, applications, and services.
- Keep public applications separated from management systems and future industrial/physical control networks.
- Dependencies and generated code require review just like handwritten code.
- Security-sensitive reports must use private disclosure channels.

## Environments

Serious products should maintain explicit environment boundaries appropriate to their maturity, commonly:

```text
Development → Staging/Acceptance → Production
```

The exact tested release should be promoted rather than rebuilt differently at each stage when practical.

## Data ownership

Shared identity, AI, notification, or infrastructure capabilities do not imply unrestricted shared databases. Each product should maintain clear ownership of its domain data, authorization rules, retention requirements, and interfaces.

## Reliability

Production systems should progressively adopt:

- health and readiness checks;
- structured logs and monitoring;
- backups and tested restoration;
- retry and idempotency for important side effects;
- controlled migrations;
- capacity and failure testing appropriate to risk;
- incident and recovery procedures.

## Human + AI development

AI-assisted engineering is encouraged when it improves speed and quality, but the accountable developer or reviewer remains responsible for:

- understanding material changes;
- validating behavior and tests;
- checking security and privacy impact;
- confirming licenses and dependency provenance;
- preventing confidential information from entering inappropriate tools or repositories;
- maintaining human approval for high-impact production, financial, safety-critical, and physical-machine actions.

## Physical and industrial systems

AI, robotics, manufacturing, drones, vehicles, and future aerospace/space systems require stricter safety boundaries than ordinary web applications. Public internet requests must not directly actuate hazardous equipment. Machine actions should pass through authenticated, constrained, observable, and independently enforceable control and safety layers appropriate to the system.

## Accessibility and usability

Public-facing products should aim for clear, consistent, responsive experiences and progressively adopt recognized accessibility practices appropriate to their users and markets.

## Continuous improvement

Standards evolve as Craniumtek grows. Simplicity is preferred over unnecessary process, but production safety, security, auditability, and clear ownership are not optional conveniences.
