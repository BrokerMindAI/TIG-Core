# TIG Core Architecture

## Overview

TIG Core is the intelligence engine behind TIG (The Intent Graph).

Its purpose is to transform publicly available business evidence into explainable commercial opportunities.

Unlike traditional business intelligence platforms, TIG is built around evidence rather than documents or companies.

Companies generate evidence.

Evidence creates signals.

Signals produce intent.

Intent becomes opportunity.

AI explains the result.

---

# High Level Architecture

```
                    PUBLIC DATA SOURCES
 ┌────────────────────────────────────────────────────────────┐
 │ Careers │ News │ Funding │ Tenders │ Websites │ RSS │ APIs │
 └────────────────────────────────────────────────────────────┘
                          │
                          ▼
                  COLLECTOR FRAMEWORK
                          │
                          ▼
                  EVIDENCE GRAPH
      (Normalized facts and relationships)
                          │
                          ▼
                   SIGNAL ENGINE
      (Business signal identification)
                          │
                          ▼
                   INTENT ENGINE
      (Industry-specific scoring models)
                          │
                          ▼
                OPPORTUNITY ENGINE
     (Ranking, prioritisation and filtering)
                          │
                          ▼
               AI INTELLIGENCE LAYER
      (Explain • Recommend • Summarise)
                          │
                          ▼
          Dashboard • API • Mobile • Integrations
```

---

# Architectural Principles

The architecture follows five core principles.

1. Separation of responsibilities.
2. Evidence is immutable.
3. Business rules are configurable.
4. AI never generates facts.
5. Every recommendation is explainable.

---

# Core Components

---

## 1. Collector Framework

Purpose

Collect raw public information.

Collectors never calculate intent.

Collectors never interpret meaning.

Responsibilities

- Retrieve data
- Validate responses
- Extract structured information
- Pass raw events to the Evidence Graph

Examples

- Careers Collector
- Funding Collector
- Company News Collector
- Website Collector
- Government Tender Collector

---

## 2. Evidence Graph

Purpose

Store normalized business facts.

The Evidence Graph is the foundation of TIG.

Everything else depends on it.

Evidence is immutable.

Evidence may be linked to

- companies
- locations
- people
- technologies
- industries
- products
- previous evidence

Example

Company

↓

Job Posted

↓

Warehouse

↓

Expansion

↓

Funding

Each relationship increases understanding.

---

Responsibilities

- Store evidence
- Validate evidence
- Track source reliability
- Track evidence confidence
- Maintain relationships
- Preserve history

---

## 3. Signal Engine

Purpose

Transform evidence into business signals.

Signals represent commercially meaningful events.

Example

Evidence

15 warehouse jobs

↓

Hiring Spike

↓

Recruitment Signal

One signal may originate from multiple evidence items.

One evidence item may generate multiple signals.

---

Responsibilities

- Pattern matching
- Signal generation
- Signal confidence
- Signal freshness
- Signal categorisation

---

## 4. Intent Engine

Purpose

Calculate commercial intent.

Intent is deterministic.

No AI is involved.

Intent uses

Evidence

+

Signals

+

Weights

+

Playbooks

↓

Intent Score

Every playbook produces different intent scores.

Examples

Recruitment

Insurance

Marketing

Cybersecurity

Payroll

---

Responsibilities

- Score calculation
- Weight application
- Confidence calculation
- Freshness decay
- Industry modifiers

---

## 5. Opportunity Engine

Purpose

Determine what users should see.

Intent does not automatically become an opportunity.

The Opportunity Engine decides

Should this appear today?

Responsibilities

- Ranking
- Prioritisation
- Deduplication
- Threshold filtering
- User relevance

---

## 6. Intelligence Layer

Purpose

Explain the engine.

The Intelligence Layer never creates evidence.

It never calculates intent.

It explains existing intelligence.

Responsibilities

- Opportunity summaries
- Outreach suggestions
- Email drafting
- Next-best actions
- Opportunity explanations

---

# Data Flow

```
Public Source

↓

Collector

↓

Raw Event

↓

Evidence Graph

↓

Signal Engine

↓

Intent Engine

↓

Opportunity Engine

↓

AI Intelligence Layer

↓

Dashboard / API
```

Every component has a single responsibility.

---

# Component Ownership

| Component | Owns |
|------------|-----------------------------|
| Collector | Data acquisition |
| Evidence Graph | Business facts |
| Signal Engine | Business signals |
| Intent Engine | Commercial intent |
| Opportunity Engine | User-facing opportunities |
| Intelligence Layer | Explanations and recommendations |

No component should perform another component's responsibilities.

---

# Explainability

Every opportunity must expose an Evidence Chain.

Example

Company

↓

Funding Round

↓

12 New Vacancies

↓

Warehouse Expansion

↓

Recruitment Intent

↓

Opportunity

Users should always understand why a recommendation exists.

---

# Configuration

Business logic should never be hardcoded.

The following should be configurable.

- Signal weights
- Freshness windows
- Industry mappings
- Opportunity thresholds
- Confidence modifiers

Configuration belongs in the database or configuration files.

---

# Scalability

The architecture must support

- Unlimited collectors
- Unlimited playbooks
- Unlimited industries
- Unlimited signals
- Multiple AI providers
- Multiple user interfaces

No redesign should be required when adding a new collector or playbook.

---

# Future Architecture

Future versions may introduce

- Relationship discovery
- Predictive modelling
- Temporal analysis
- Industry benchmarking
- Graph analytics
- Learning engine

These capabilities should build upon the existing architecture rather than replace it.

---

# Summary

The architecture is intentionally modular.

Evidence remains the single source of truth.

Signals interpret evidence.

Intent evaluates signals.

Opportunities prioritise intent.

AI explains everything.

This separation ensures TIG remains transparent, explainable and extensible as it grows.
