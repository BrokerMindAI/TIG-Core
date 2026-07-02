# Collector Framework

Version

v0.1

---

# Purpose

The Collector Framework defines the contract that every TIG collector must follow.

Collectors are responsible for discovering and extracting public business information.

Collectors do **not** interpret business meaning.

Collectors do **not** calculate intent.

Collectors do **not** interact with AI.

Their sole responsibility is to transform external data into standardized Evidence Records.

---

# Design Principles

Every collector must be:

- Stateless
- Idempotent
- Deterministic
- Modular
- Independently deployable
- Independently testable
- Versioned

---

# Collector Lifecycle

```
Scheduler

↓

Collector

↓

Fetch

↓

Extract

↓

Normalize

↓

Validate

↓

Deduplicate

↓

Emit Evidence

↓

Evidence Ingestion Service

↓

Evidence Graph
```

---

# Responsibilities

Collectors MAY:

- Fetch public data
- Call public APIs
- Crawl websites
- Parse HTML
- Parse JSON
- Parse XML
- Detect changes
- Normalize fields
- Validate required fields
- Emit Evidence Records

Collectors MUST NOT:

- Calculate Signals
- Calculate Intent
- Score companies
- Call LLMs
- Generate Opportunities
- Modify existing Evidence
- Update scoring rules

---

# Collector Interface

Every collector implements the following interface.

```typescript
interface Collector {

initialize()

fetch()

extract()

normalize()

validate()

deduplicate()

emit()

shutdown()

}
```

---

# Lifecycle Methods

## initialize()

Loads configuration.

Initializes authentication.

Loads cache.

Registers collector.

---

## fetch()

Downloads raw source data.

Examples

- API
- RSS
- Careers Page
- HTML
- XML
- CSV

Returns

Raw payload.

---

## extract()

Extracts meaningful business objects.

Examples

Jobs

Funding

Leadership

Technology

Tenders

---

## normalize()

Maps extracted objects into TIG's canonical Evidence schema.

No collector may invent new fields.

---

## validate()

Checks

Required fields

Timestamp

Company

Category

Confidence

Metadata

---

## deduplicate()

Ensures duplicate evidence is not emitted.

Duplicate detection should compare

- Source
- Company
- Event Type
- Timestamp
- Metadata fingerprint

---

## emit()

Outputs one or more Evidence Records.

Collectors never write directly to the database.

Collectors emit standardized messages to the Evidence Ingestion Service.

---

## shutdown()

Closes resources.

Flushes buffers.

Logs metrics.

---

# Evidence Contract

Every collector MUST emit:

```json
{
  "collector": "careers",
  "version": "1.0.0",
  "records": [
    {
      "company_id": "...",
      "event_type": "...",
      "category": "...",
      "observed_at": "...",
      "confidence": 99,
      "metadata": {}
    }
  ]
}
```

---

# Collector Registration

Every collector registers itself.

Example

```yaml
collector:

id: careers

version: 1.0.0

owner: TIG

status: active

schedule: hourly

source_type: Careers

output_schema: evidence.v1

health_endpoint: /health

```

---

# Collector Metadata

Each collector stores

- Version
- Last Run
- Average Runtime
- Success Rate
- Error Rate
- Records Collected
- Records Emitted

---

# Collector Health

Possible states

Healthy

Running

Paused

Failed

Deprecated

Disabled

---

# Retry Strategy

Transient failures

Retry with exponential backoff.

Permanent failures

Log

Alert

Stop

Collectors must never enter infinite retry loops.

---

# Scheduling

Collectors should support

Manual

Hourly

Daily

Weekly

Cron

Event-driven

Scheduling is external to collectors.

Collectors never schedule themselves.

---

# Logging

Collectors should log

Start

Finish

Duration

Errors

Warnings

Records Processed

Duplicates Removed

---

# Metrics

Recommended metrics

collection_duration

records_collected

records_emitted

validation_failures

duplicates

errors

success_rate

---

# Security

Collectors may only access:

Public information

Approved APIs

Configured credentials

Collectors never store credentials internally.

Secrets are managed externally.

---

# Testing

Every collector must include

Unit Tests

Integration Tests

Sample Payloads

Mock Responses

Validation Tests

Deduplication Tests

---

# Collector Directory

Example

collectors/

careers/

funding/

news/

website/

linkedin/

tenders/

github/

rss/

---

# Future Collectors

Examples

Careers

Funding

Government Tenders

Company Websites

News

Patent Filings

App Store

GitHub

LinkedIn

Job Boards

Technology Detection

Social Media

---

# Success Criteria

A compliant collector

✓ Produces standardized Evidence

✓ Never calculates intent

✓ Is independently deployable

✓ Is fully testable

✓ Can be upgraded independently

✓ Can be replaced without affecting other collectors

---

# Summary

Collectors are the eyes of TIG.

They observe.

They collect.

They normalize.

They emit.

They never think.

Thinking belongs to the intelligence engines.
