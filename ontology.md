# TIG Ontology

Version

v0.1

---

# Purpose

The TIG Ontology defines every object, event and relationship that exists within The Intent Graph.

It provides a shared language for every component of TIG Core.

All collectors, evidence records, signals, intent calculations and AI explanations must conform to this ontology.

The ontology is the semantic foundation of the platform.

---

# Design Philosophy

TIG models the business world as a graph rather than a collection of tables.

Everything is either:

- Entity
- Event
- Relationship

Events generate Evidence.

Evidence generates Signals.

Signals generate Intent.

Intent generates Opportunities.

---

# High Level Model

```

Entities

↓

Events

↓

Evidence

↓

Signals

↓

Intent

↓

Opportunities

```

---

# Entity Types

Entities represent things that exist.

Entities have identity.

Entities persist over time.

---

## Company

Represents an organisation.

Examples

- Microsoft
- DHL
- Tesla
- ABC Logistics

Attributes

- Name
- Industry
- Website
- Employee Count
- Country
- Company Size
- Status

---

## Person

Represents an individual.

Examples

- CEO
- HR Manager
- Founder
- Recruiter

Attributes

- Name
- Title
- LinkedIn
- Department

---

## Job

Represents an advertised role.

Attributes

- Title
- Department
- Location
- Employment Type
- Posted Date
- Closing Date

---

## Office

Represents a physical location.

Attributes

- Address
- City
- Country
- Opened Date

---

## Warehouse

Represents a logistics facility.

Attributes

- Capacity
- Location
- Type

---

## Technology

Represents software or platforms used by a company.

Examples

- Salesforce
- HubSpot
- SAP
- AWS

---

## Product

Represents a commercial product or service.

---

## Funding Round

Represents an investment event.

Examples

- Seed
- Series A
- Series B

---

## Tender

Represents a procurement opportunity.

---

## Website

Represents a company's digital presence.

---

## Industry

Represents an economic sector.

Examples

- Logistics
- Healthcare
- Construction

---

## Playbook

Represents an industry-specific scoring profile.

Examples

- Recruitment
- Marketing
- Insurance
- Cybersecurity

---

## Evidence

Represents an observed business fact.

Evidence is immutable.

---

## Signal

Represents a commercially meaningful interpretation of evidence.

---

## Intent

Represents calculated buying probability.

---

## Opportunity

Represents a surfaced recommendation.

---

# Event Types

Events happen.

Events are observed.

Events generate Evidence.

Examples

- Job Posted
- Job Closed
- Office Opened
- Office Closed
- Funding Announced
- CEO Appointed
- Partnership Announced
- Product Released
- Tender Published
- Website Updated
- Patent Filed
- Acquisition Completed

---

# Relationship Types

Relationships connect entities.

---

Company

HAS_JOB

Job

---

Company

HAS_OFFICE

Office

---

Company

HAS_WAREHOUSE

Warehouse

---

Company

USES

Technology

---

Company

EMPLOYS

Person

---

Company

OPERATES_IN

Industry

---

Company

OWNS

Website

---

Company

RECEIVED

Funding Round

---

Company

PUBLISHED

Tender

---

Company

GENERATED

Evidence

---

Evidence

CREATED

Signal

---

Signal

CONTRIBUTES_TO

Intent

---

Intent

GENERATES

Opportunity

---

Opportunity

USES

Playbook

---

Person

WORKS_FOR

Company

---

Office

LOCATED_IN

City

---

Warehouse

LOCATED_IN

City

---

Technology

BELONGS_TO

Category

---

# Graph Example

```

ABC Logistics

│

├── HAS_OFFICE

│       Melbourne

│

├── HAS_WAREHOUSE

│       Truganina

│

├── USES

│       SAP

│

├── EMPLOYS

│       HR Manager

│

├── GENERATED

│       Job Posted

│

└── RECEIVED

        Funding

```

---

# Entity Rules

Every entity must

- Have a unique ID
- Have a type
- Support relationships
- Support metadata
- Support versioning

---

# Relationship Rules

Relationships

- are directional
- may contain metadata
- may expire
- may change over time

Relationships should never duplicate entity data.

---

# Event Rules

Events

- occur at a point in time
- generate evidence
- are immutable
- may involve multiple entities

---

# Ontology Principles

The ontology must be

Consistent

Extensible

Versioned

Explainable

Reusable

Industry Agnostic

---

# Future Entity Types

Future versions may introduce

- Fleet
- Vehicle
- Property
- Manufacturing Plant
- Supplier
- Customer
- Contract
- Regulation
- Certification
- Invoice
- Shipment

---

# Future Relationship Types

Examples

SUPPLIES

PARTNERS_WITH

COMPETES_WITH

INVESTED_IN

LOCATED_NEAR

USES_VENDOR

REPORTED_BY

INSURES

HIRES

SERVICES

---

# Summary

The TIG Ontology is the shared language of the platform.

Everything inside TIG is represented as an Entity, Event or Relationship.

This model allows collectors, signals, playbooks and AI to operate using the same semantic structure while remaining modular and extensible.
