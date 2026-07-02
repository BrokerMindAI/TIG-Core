# TIG Core

> The intelligence engine behind TIG (The Intent Graph).

TIG Core is responsible for transforming publicly available business evidence into structured commercial intelligence.

Rather than aggregating news, TIG Core identifies business signals, calculates industry-specific intent scores, and generates actionable opportunities.

The frontend (TIG Web) is simply one interface to the engine.

---

## Vision

Businesses leave thousands of public signals every day.

Hiring.
Funding.
Leadership changes.
Office expansions.
Government tenders.
Website updates.

Individually these events mean very little.

Together they reveal commercial intent.

TIG Core exists to detect, normalize and interpret those signals before they become obvious to everyone else.

---

## Core Pipeline

```
Collectors
      │
      ▼
Evidence Engine
      │
      ▼
Signal Library
      │
      ▼
Intent Engine
      │
      ▼
Opportunity Engine
      │
      ▼
AI Intelligence Layer
      │
      ▼
Dashboard / API
```

---

## Repository Structure

```
tig-core/

docs/
schemas/
weights/
collectors/
examples/
tests/
```

---

## Core Components

### Collectors

Collect raw public business information.

Examples:

- Careers Pages
- Government Tenders
- Company News
- Funding Announcements
- Websites
- RSS Feeds

---

### Evidence Engine

Normalizes raw events into a consistent evidence model.

---

### Signal Library

Converts evidence into standardized business signals.

Examples:

- Hiring Spike
- Office Expansion
- Funding Round
- Executive Change
- Product Launch

---

### Intent Engine

Calculates commercial intent using configurable scoring models.

Every industry has different weights.

---

### Opportunity Engine

Determines which companies should appear to the user today.

---

### AI Layer

AI never creates opportunities.

AI explains opportunities.

---

## Design Goals

- Explainable
- Evidence-based
- Modular
- Industry agnostic
- Extensible
- Transparent

---

## Long-Term Vision

Become the world's most trusted commercial intent intelligence platform.
