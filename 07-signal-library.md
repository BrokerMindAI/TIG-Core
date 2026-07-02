# Signal Library

Version

v0.1

---

# Purpose

The Signal Library defines every commercially meaningful business signal recognised by TIG.

Signals transform raw evidence into business intelligence.

Signals do not predict intent.

Signals describe meaningful business events.

Intent is calculated later by the Intent Engine.

---

# Signal Pipeline

```
Evidence

↓

Pattern Detection

↓

Signal

↓

Intent Engine

↓

Opportunity Engine
```

---

# What is a Signal?

A Signal represents a commercially significant business event inferred from one or more pieces of evidence.

Signals are:

- Explainable
- Configurable
- Reusable
- Industry agnostic

Signals never contain AI-generated assumptions.

---

# Signal Structure

Every signal contains

| Field | Description |
|---------|-------------|
| Signal ID | Unique identifier |
| Name | Human readable name |
| Category | Hiring, Funding etc |
| Description | What the signal means |
| Evidence Required | Required evidence types |
| Pattern | Detection logic |
| Confidence | Signal confidence |
| Freshness | Validity period |
| Default Weight | Base score |
| Industries | Relevant industries |
| Suggested Actions | Recommended next step |

---

# Signal Categories

Current categories

- Hiring
- Funding
- Expansion
- Leadership
- Technology
- Procurement
- Compliance
- Infrastructure
- Partnerships
- Financial
- Marketing

---

# Signal Anatomy

```
Evidence

↓

Pattern

↓

Signal

↓

Intent
```

---

# Example Signal

## SIG-001

Name

Hiring Spike

Category

Hiring

Description

A company is rapidly increasing recruitment activity.

Pattern

10+ new vacancies within 30 days.

Evidence Required

Job Posted

Department

Location

Observed Date

Confidence

95%

Freshness

90 Days

Default Weight

25

Industries

Recruitment

Payroll

Insurance

Cybersecurity

HR Software

Suggested Actions

Contact Talent Acquisition.

Offer recruitment support.

---

## SIG-002

Long Open Vacancy

Category

Hiring

Pattern

Job open longer than 90 days.

Confidence

92%

Freshness

120 Days

Weight

18

Industries

Recruitment

HR Software

Suggested Actions

Offer hard-to-fill recruitment services.

---

## SIG-003

Funding Round

Category

Funding

Pattern

Official funding announcement.

Confidence

98%

Freshness

180 Days

Weight

30

Industries

Marketing

Recruitment

Payroll

Insurance

Technology

---

## SIG-004

Office Expansion

Category

Expansion

Pattern

New office opened.

Confidence

97%

Freshness

120 Days

Weight

22

Industries

Insurance

Marketing

Recruitment

Furniture

Payroll

---

## SIG-005

Executive Appointment

Category

Leadership

Pattern

New C-Level executive announced.

Confidence

95%

Freshness

180 Days

Weight

20

Industries

Consulting

Marketing

Technology

---

# Pattern Detection

Signals are created from patterns.

Patterns may consist of

One Evidence Item

Example

Funding Announcement

↓

Funding Signal

Or

Multiple Evidence Items

Example

15 Job Postings

+

Two New Offices

+

New Warehouse

↓

Growth Signal

---

# Composite Signals

Some signals are built from multiple smaller signals.

Example

Hiring Spike

+

Funding

+

Expansion

↓

High Growth

Composite signals may produce stronger intent.

---

# Signal Freshness

Every signal expires.

Example

| Signal | Freshness |
|---------|-----------|
| Hiring Spike | 90 days |
| Funding | 180 days |
| Website Update | 30 days |
| Tender | Until Closing |
| CEO Change | 365 days |

---

# Signal Confidence

Signal confidence depends on

Evidence Confidence

+

Source Reliability

+

Pattern Strength

↓

Signal Confidence

---

# Industry Mapping

Signals are reusable.

Example

Funding

↓

Recruitment

Marketing

Insurance

Cybersecurity

Payroll

Different industries apply different weights.

---

# Weighting

Signal weights are defaults only.

Playbooks override weights.

Example

Funding

Recruitment

15

Marketing

35

Insurance

8

---

# Versioning

Signals evolve.

Existing Signal IDs never change.

Weights may change.

Patterns may improve.

Descriptions may expand.

Historical compatibility must be maintained.

---

# Signal Relationships

Signals may generate

Other Signals.

Example

Hiring Spike

↓

Growth Signal

↓

Expansion Signal

↓

Recruitment Intent

Signal relationships create the Signal Graph.

---

# Signal Quality Rules

Every signal must satisfy

✓ Explainable

✓ Repeatable

✓ Configurable

✓ Evidence-backed

✓ Industry agnostic

If a signal fails any rule,

it should not exist.

---

# Initial Signal Roadmap

Phase One

50 Signals

Phase Two

150 Signals

Phase Three

300+

Signals

Future

Unlimited

Signals

---

# Design Principles

Signals should be

Simple

Independent

Reusable

Auditable

Composable

Configurable

Transparent

---

# Summary

Signals transform evidence into commercially meaningful events.

They provide the bridge between raw business activity and calculated commercial intent.

The Signal Library is one of the core intellectual assets of TIG.
