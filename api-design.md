# API Design

Version

v0.1

---

# Purpose

The TIG API provides standardized interfaces for communication between internal services, collectors, user applications and external integrations.

The API is divided into multiple logical interfaces rather than a single monolithic API.

This separation improves security, scalability and maintainability.

---

# API Philosophy

The API follows five principles.

- Resource-oriented
- Versioned
- Stateless
- Explainable
- Backwards compatible

Every response should be deterministic.

---

# API Architecture

```
                 Frontend

                     │

                Public API

                     │

────────────────────────────────────

Internal Services

Collector Framework

AI Layer

Admin

────────────────────────────────────

                 TIG Core
```

---

# API Categories

TIG exposes five APIs.

| API | Purpose |
|------|----------|
| Public API | Customer applications |
| Internal API | Engine communication |
| Collector API | Evidence ingestion |
| Intelligence API | AI explanations |
| Admin API | Monitoring & operations |

---

# 1. Public API

Purpose

Expose commercial intelligence to customers.

Authentication

JWT

OAuth

API Keys

Example Endpoints

GET /companies

GET /companies/{id}

GET /opportunities

GET /signals

GET /evidence

GET /playbooks

GET /notifications

POST /feedback

POST /saved-searches

---

Example Response

```json
{
    "company":"ABC Logistics",
    "intent_score":91,
    "confidence":96,
    "playbook":"Recruitment"
}
```

---

# 2. Internal API

Purpose

Communication between TIG engines.

Never exposed publicly.

Example

POST /internal/evidence

POST /internal/signals

POST /internal/intent

POST /internal/opportunities

GET /internal/playbooks

GET /internal/config

---

# 3. Collector API

Purpose

Accept Evidence Records from collectors.

Collectors never write directly to PostgreSQL.

Collectors submit standardized Evidence payloads.

POST

/collector/evidence

POST

/collector/heartbeat

POST

/collector/status

GET

/collector/config

---

Example

```json
{
  "collector":"careers",
  "version":"1.0",
  "records":[]
}
```

---

# 4. Intelligence API

Purpose

AI explanations.

The Intelligence API never generates Evidence.

It never calculates Intent.

It only explains existing intelligence.

Endpoints

POST /ai/explain

POST /ai/summarize

POST /ai/recommend

POST /ai/email

POST /ai/account-brief

---

Example

Input

Opportunity

↓

Output

Summary

Suggested Email

Talking Points

Next Action

---

# 5. Admin API

Purpose

Platform operations.

Examples

GET /health

GET /metrics

GET /collectors

GET /collector-runs

GET /audit

GET /jobs

GET /system

POST /collectors/run

POST /collectors/pause

POST /collectors/resume

---

# Versioning

Every API is versioned.

Examples

/v1/companies

/v1/opportunities

/v2/opportunities

Breaking changes require a new version.

---

# Authentication

Supported methods

JWT

OAuth 2

API Keys

Future

SAML

OIDC

---

# Authorization

Role Based Access Control

Examples

Admin

Customer

Viewer

Collector

Internal Service

AI Service

---

# Error Format

Every endpoint returns the same structure.

```json
{
    "success":false,
    "error":{
        "code":"NOT_FOUND",
        "message":"Company not found"
    }
}
```

---

# Pagination

Standard pagination.

Example

GET

/companies?page=2&limit=50

Response

```json
{
    "page":2,
    "limit":50,
    "total":2400,
    "results":[]
}
```

---

# Filtering

Examples

industry=

country=

playbook=

signal=

intent_min=

confidence_min=

date_from=

date_to=

---

# Sorting

Examples

sort=intent_score

sort=confidence

sort=created_at

sort=company

---

# Webhooks

Customers may subscribe to

New Opportunity

Intent Updated

Collector Failed

Evidence Added

Signal Created

---

# Rate Limits

Public API

100 requests/minute

Internal API

Unlimited

Collector API

Unlimited (authenticated)

Admin API

Restricted

---

# Observability

Every request includes

Request ID

Timestamp

Latency

User ID

Version

---

# API Contracts

Every endpoint returns

- success
- metadata
- data
- errors

Responses must be consistent across all APIs.

---

# OpenAPI

Every endpoint should be documented using OpenAPI 3.1.

Documentation should be generated automatically.

---

# Future APIs

GraphQL

gRPC

Streaming API

Webhook Events

SDKs

Python

TypeScript

Go

Rust

---

# Summary

The TIG API is divided into specialised interfaces that separate customer access, internal services, collectors, AI capabilities and administrative operations.

This modular architecture supports future scaling while maintaining security and clear ownership.
