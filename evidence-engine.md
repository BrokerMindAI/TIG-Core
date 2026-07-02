# Evidence Engine

## Version

v0.1

---

# Purpose

The Evidence Engine is responsible for transforming raw public information into standardized, trustworthy and reusable business evidence.

The Evidence Engine is the foundation of TIG Core.

Every downstream component—including the Signal Engine, Intent Engine and AI Intelligence Layer—depends entirely on evidence.

If the Evidence Engine fails, the rest of the platform becomes unreliable.

---

# Philosophy

Evidence represents observed facts.

Evidence never contains opinions.

Evidence never predicts outcomes.

Evidence is immutable.

Evidence is explainable.

Evidence is reusable.

---

# Evidence Lifecycle

```
Public Source

↓

Collector

↓

Raw Event

↓

Validation

↓

Normalization

↓

Evidence Record

↓

Relationship Mapping

↓

Evidence Graph

↓

Signal Engine
```

Every collector follows this exact pipeline.

---

# Evidence Lifecycle States

Every evidence item moves through the following states.

```
Collected

↓

Validated

↓

Normalized

↓

Linked

↓

Active

↓

Archived
```

---

## Collected

The raw event has been retrieved.

No assumptions have been made.

---

## Validated

The source has been checked.

The payload is complete.

Duplicate detection has occurred.

---

## Normalized

The raw event has been converted into TIG's standard format.

---

## Linked

Relationships are created.

Examples

Company

↓

Location

↓

Technology

↓

Industry

↓

People

↓

Previous Evidence

---

## Active

The evidence contributes to scoring.

---

## Archived

Evidence is retained but no longer contributes to scoring due to freshness decay.

---

# Evidence Record

Every evidence item must contain the following fields.

| Field | Required | Description |
|---------|----------|-------------|
| evidence_id | Yes | Unique identifier |
| company_id | Yes | Company reference |
| collector | Yes | Collector that produced the evidence |
| source | Yes | Original source URL or identifier |
| source_type | Yes | Careers, News, Website, Tender etc |
| event_type | Yes | Raw observed event |
| category | Yes | Hiring, Funding, Expansion etc |
| title | Yes | Human-readable summary |
| description | No | Longer explanation |
| observed_at | Yes | When the event occurred |
| collected_at | Yes | When TIG collected it |
| normalized_at | Yes | When normalization completed |
| confidence | Yes | 0–100 |
| source_reliability | Yes | A–D |
| metadata | Yes | Flexible JSON payload |
| status | Yes | Lifecycle state |

---

# Example Evidence Record

```json
{
  "evidence_id": "EV-000001",
  "company_id": "COMP-001",
  "collector": "careers",
  "source": "https://company.com/careers",
  "source_type": "Careers",
  "event_type": "Job Posted",
  "category": "Hiring",
  "title": "Senior Warehouse Manager",
  "description": "Warehouse leadership position advertised.",
  "observed_at": "2026-07-03T09:15:00Z",
  "collected_at": "2026-07-03T09:20:00Z",
  "normalized_at": "2026-07-03T09:20:03Z",
  "confidence": 99,
  "source_reliability": "A",
  "status": "Active",
  "metadata": {
      "location":"Melbourne",
      "department":"Operations",
      "employment_type":"Full Time"
  }
}
```

---

# Source Reliability

Source reliability measures trustworthiness.

It does not measure confidence.

| Rating | Description |
|---------|-------------|
| A | Official company or government source |
| B | Trusted third-party publication |
| C | Community or indirect source |
| D | Unverified source |

Examples

A

Company Careers Page

Government Website

Official Press Release

B

Reuters

Bloomberg

Major Industry Publication

C

Trade Blog

Industry Forum

D

Social Media Rumour

Anonymous Source

---

# Evidence Confidence

Evidence Confidence measures how certain TIG is that the evidence has been correctly interpreted.

Examples

Official job listing

Confidence

99%

Funding article mentioning possible investment

Confidence

70%

Rumoured office expansion

Confidence

35%

---

# Evidence Categories

Current supported categories

- Hiring
- Funding
- Expansion
- Leadership
- Procurement
- Marketing
- Technology
- Partnerships
- Compliance
- Infrastructure
- Financial
- Legal

New categories can be added without modifying existing collectors.

---

# Metadata

Metadata contains collector-specific information.

Hiring Example

```json
{
    "job_title":"Warehouse Manager",
    "department":"Operations",
    "location":"Sydney",
    "employment_type":"Full Time"
}
```

Funding Example

```json
{
    "round":"Series A",
    "amount":"25000000",
    "currency":"USD",
    "lead_investor":"ABC Ventures"
}
```

Website Example

```json
{
    "page":"Homepage",
    "change":"New Service",
    "technology":"Next.js"
}
```

---

# Validation Rules

Evidence must satisfy the following rules.

- Source must exist.
- Company must exist or be created.
- Timestamp required.
- Category required.
- Confidence between 0–100.
- Duplicate detection performed.
- Metadata must be valid JSON.

Evidence failing validation enters the Rejected state.

---

# Duplicate Detection

Duplicate evidence should not create duplicate signals.

Collectors should compare

- Source
- Event Type
- Timestamp
- Company
- Metadata fingerprint

before creating a new evidence record.

---

# Freshness

Evidence decays over time.

Example

| Category | Freshness |
|------------|----------|
| Funding | 180 days |
| Hiring | 120 days |
| Website | 60 days |
| Tender | 30 days |
| Leadership | 365 days |

Freshness values are configurable.

---

# Relationships

Evidence may be linked to

- Company
- Person
- Technology
- Product
- Industry
- Location
- Existing Evidence

These relationships form the Evidence Graph.

---

# Versioning

Evidence should never be overwritten.

If new information is discovered,

create a new evidence record.

Historical evidence remains available for auditing.

---

# Security

Evidence is immutable.

Users may annotate evidence.

Users may never modify evidence.

System administrators may archive evidence.

---

# Evidence API Contract

Every collector must output this minimum payload.

```json
{
  "company_id":"",
  "collector":"",
  "source":"",
  "event_type":"",
  "category":"",
  "observed_at":"",
  "confidence":100,
  "metadata":{}
}
```

Collectors producing different formats are considered non-compliant.

---

# Success Criteria

The Evidence Engine succeeds when

- Every collector outputs identical structures.
- Evidence is reusable across industries.
- Every opportunity is traceable.
- Every score is explainable.
- Evidence is immutable.
- Relationships are preserved.

---

# Guiding Principle

The Evidence Engine is the single source of truth.

Everything else in TIG is derived from evidence.
