# Starter Azure platform profile

This is an adaptable starting point for estimating extensions to an existing Azure data/API platform, not a description of a particular client's environment. Confirm which services and patterns apply to the current project. Replace or supplement this profile with an organization-specific reference when needed.

## Intended baseline to confirm

The workflow targets projects that normally extend existing shared services. Do not estimate building a new platform unless the confirmed scope requires it. The presence of a service in this list does not mean the current project uses or changes it.

| Component | Scope to check |
| --- | --- |
| Databricks ingestion | Sources, ingestion changes, schema and data-quality checks |
| Databricks transformations / Silver data | Business rules, available source fields, transformations, reconciliation and tests |
| ODS and API datasets consumed by .NET | Lineage, data contracts, refresh timing, serving mechanism and acceptance |
| .NET APIs | Response attributes, endpoints, contracts, authentication, error handling and tests |
| App Service | Application configuration and deployment impact |
| APIM | API exposure, policies, subscriptions and versioning impact |
| ADF | Orchestration, triggers, external readiness and failure handling |
| Storage | Paths, permissions, retention and data movement |
| Azure DevOps | Existing build/release paths, environments and approvals |

Typical role vocabulary: Data Engineer, Data Analyst, .NET Developer, DevOps Engineer and Technical SME. Use the roles and labels agreed for the project; review hours vary by task. Team ownership is separate from role.

## Project-specific confirmations

Confirm the relevant ingestion patterns, layer conventions, dataset serving mechanism, identity/security patterns, environments, API contract/versioning, orchestration ownership, CI/CD reuse, test/release responsibilities and external lead times. Do not treat unknown patterns as established facts or invent available capacity.

Keep project assumptions in project notes. For any reusable organization-specific pattern, record applicability, exceptions, confirming source and date, with the owner's agreement before modifying shared guidance.
