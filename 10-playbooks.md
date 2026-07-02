# Playbooks

Version

v0.1

---

# Purpose

Playbooks define how TIG interprets business intelligence for a specific use case.

A Playbook transforms generic business signals into industry-specific opportunities.

Signals remain universal.

Interpretation changes.

---

# Philosophy

TIG does not believe there is a single definition of buying intent.

Buying intent depends on context.

Example

A hiring spike may indicate:

- Recruitment opportunity
- Payroll opportunity
- HR software opportunity
- Employee benefits opportunity

The evidence is identical.

The interpretation differs.

---

# Architecture

```
Evidence

↓

Pattern Engine

↓

Signals

↓

Playbook

↓

Intent Score

↓

Opportunity
```

---

# Playbook Components

Every playbook contains:

- Metadata
- Supported Industries
- Target Personas
- Signal Weights
- Signal Overrides
- Composite Signals
- Negative Signals
- Freshness Rules
- Thresholds
- Recommended Actions
- AI Prompt Templates

---

# Playbook Metadata

Example

```yaml
id: recruitment

name: Recruitment

version: 1.0.0

owner: TIG

status: Active

description: Detects companies likely to require recruitment services.
```

---

# Target Personas

Examples

- Recruitment Agency
- Insurance Broker
- Payroll Provider
- Marketing Agency
- Cybersecurity Consultant
- IT MSP
- Commercial Finance Broker
- Equipment Supplier

---

# Signal Categories

Examples

Hiring

Funding

Expansion

Technology

Compliance

Leadership

Marketing

Procurement

Financial

Infrastructure

---

# Signal Weights

Example

| Signal | Weight |
|---------|-------:|
| Hiring Spike | 30 |
| Long Vacancy | 25 |
| Funding | 15 |
| Expansion | 20 |
| Executive Appointment | 10 |
| Website Update | 2 |

Weights are configurable.

---

# Signal Overrides

Playbooks may override default signal behaviour.

Example

Funding

Default Weight

30

Recruitment Playbook

15

Marketing Playbook

35

Insurance Playbook

8

---

# Composite Signals

Multiple signals may create stronger intent.

Example

Hiring Spike

+

Funding

+

Expansion

↓

Growth Momentum

Composite signals receive their own score.

---

# Negative Signals

Examples

- Hiring Freeze
- Mass Layoffs
- Office Closure
- Bankruptcy
- Funding Withdrawal

Negative signals reduce intent.

---

# Freshness

Signals expire differently by playbook.

Example

Recruitment

Hiring Spike

90 Days

Insurance

Expansion

180 Days

Marketing

Website Update

30 Days

---

# Thresholds

Each playbook defines:

Minimum Intent Score

Minimum Confidence

Minimum Evidence Count

Minimum Signal Diversity

---

# Opportunity Generation

If thresholds are satisfied

↓

Opportunity Engine creates opportunity.

Otherwise

↓

Signals remain stored for future evaluation.

---

# Recommended Actions

Every playbook defines suggested actions.

Example

Recruitment

- Call HR Manager
- Send Talent Market Report
- Offer Recruitment Support

Marketing

- Offer Website Audit
- Discuss Lead Generation
- Propose SEO Strategy

Insurance

- Review Business Coverage
- Offer Risk Assessment
- Discuss Policy Renewal

---

# AI Templates

Playbooks may include reusable AI prompts.

Example

Recruitment

Generate

- Cold Email
- LinkedIn Message
- Discovery Questions
- Call Script

AI never changes intent scores.

AI only explains opportunities.

---

# Versioning

Playbooks are versioned.

Historical intent calculations remain reproducible.

---

# Testing

Every playbook should include:

- Weight validation
- Threshold tests
- Composite signal tests
- Negative signal tests
- Opportunity generation tests

---

# Example Playbooks

Core library

- Recruitment
- Insurance
- Marketing
- Cybersecurity
- Payroll
- Commercial Finance
- IT Services
- Logistics
- Legal Services
- Accounting

---

# Future Playbooks

Community Playbooks

Partner Playbooks

Customer-defined Playbooks

AI-assisted Playbooks (explainability only)

---

# Design Principles

Playbooks must be:

- Modular
- Explainable
- Configurable
- Versioned
- Testable
- Independent

---

# Summary

Playbooks are TIG's decision models.

They enable the same business evidence to generate different commercial opportunities depending on the needs of the customer.

Signals are universal.

Playbooks provide context.
