# TIG Glossary

This glossary defines the core terminology used throughout TIG Core.

These definitions are the single source of truth and should remain consistent across all documentation, code, APIs and playbooks.

---

# Evidence

The smallest unit of verified business information collected from a public source.

Evidence represents an observed fact—not an interpretation.

Examples:

- A company posted a new job.
- A funding round was announced.
- A warehouse opened.
- A new CEO was appointed.

Evidence always contains:

- Source
- Timestamp
- Confidence
- Metadata

Evidence never contains opinions.

---

# Collector

A software component responsible for retrieving public business information from a specific source.

Examples:

- Careers Collector
- Company News Collector
- Funding Collector
- Tender Collector
- Website Change Collector

Collectors do not calculate intent.

Their only responsibility is to collect and normalize data.

---

# Raw Event

The original information collected before normalization.

Example:

"We're excited to announce our new Melbourne office."

This is not yet evidence.

---

# Normalization

The process of converting raw events into standardized evidence.

Example:

Raw Event

"We're opening a new warehouse in Brisbane."

↓

Evidence

Category:
Office Expansion

Location:
Brisbane

Confidence:
98%

---

# Evidence Engine

The subsystem responsible for validating, normalizing and storing evidence.

It ensures all collectors produce a consistent output format regardless of source.

---

# Signal

A business event inferred from one or more pieces of evidence.

Signals have commercial meaning.

Examples:

- Hiring Spike
- Office Expansion
- Funding Round
- Executive Change
- Product Launch
- Website Redesign

Signals are reusable across industries.

---

# Signal Library

The complete catalogue of all supported business signals.

Each signal contains:

- Definition
- Required Evidence
- Industries
- Weight
- Confidence
- Freshness
- Suggested Actions

The Signal Library is one of TIG's core intellectual assets.

---

# Intent

The calculated probability that a company is likely to require a particular product or service.

Intent is never guessed.

Intent is calculated using evidence and signal weights.

Examples:

- Recruitment Intent
- Marketing Intent
- Insurance Intent
- Cybersecurity Intent

---

# Intent Score

A numerical score representing the strength of a company's commercial intent within a specific playbook.

Scores are calculated using configurable business rules.

Scores should always be explainable.

---

# Opportunity

A high-confidence recommendation presented to the user.

An Opportunity is generated when intent exceeds a predefined threshold.

Example:

Company:
ABC Logistics

Opportunity:
Recruitment

Confidence:
94%

Reason:
Multiple long-open vacancies and rapid hiring expansion.

---

# Opportunity Feed

The ranked stream of opportunities presented to users.

The feed prioritizes opportunities using:

- Intent Score
- Confidence
- Freshness
- Industry Relevance

---

# Evidence Chain

The complete sequence of evidence supporting an opportunity.

Example

Funding

↓

Hiring Spike

↓

Office Expansion

↓

High Recruitment Intent

Every opportunity must expose its evidence chain.

---

# Confidence

A measurement of certainty.

TIG distinguishes multiple confidence levels.

---

## Evidence Confidence

How certain TIG is that a piece of evidence has been correctly interpreted.

Example:

Official company careers page

Confidence:
99%

---

## Source Reliability

A rating describing how trustworthy the original source is.

Levels:

A — Official

B — Trusted Third Party

C — Community Source

D — Unverified

---

## Intent Confidence

The overall confidence in the calculated intent score.

Intent Confidence considers:

- Evidence quality
- Source reliability
- Number of supporting signals
- Signal agreement

---

# Freshness

The remaining value of evidence over time.

Recent evidence has greater influence than historical evidence.

Each signal defines its own freshness period.

---

# Weight

A configurable numerical value assigned to a signal.

Weights determine how much influence a signal contributes to an Intent Score.

Weights are stored in configuration—not hardcoded.

---

# Playbook

An industry-specific scoring configuration.

Playbooks determine which signals matter most for different users.

Examples:

- Recruitment
- Marketing
- Insurance
- Logistics
- Cybersecurity

The same evidence may produce different intent scores across different playbooks.

---

# Collector Framework

The standardized interface all collectors must follow.

Every collector performs four steps:

1. Collect
2. Validate
3. Normalize
4. Store Evidence

---

# Evidence Database

The centralized repository of all normalized evidence collected by TIG.

The Evidence Database is the foundation of the platform.

Intent Scores can always be recalculated from stored evidence.

---

# Intent Engine

The subsystem responsible for calculating commercial intent from evidence and signal weights.

The Intent Engine is deterministic and explainable.

It does not use generative AI to make decisions.

---

# Opportunity Engine

The subsystem responsible for deciding which opportunities should be surfaced to users.

The Opportunity Engine evaluates:

- Intent Score
- Confidence
- Freshness
- Industry relevance
- User playbook

---

# AI Intelligence Layer

The AI component responsible for explaining opportunities and recommending actions.

Responsibilities include:

- Summarization
- Opportunity explanations
- Outreach suggestions
- Prioritization
- Email drafting

The AI layer never creates evidence or intent.

---

# Evidence Graph

The interconnected network of companies, evidence, signals and opportunities.

The Evidence Graph allows TIG to understand relationships between business events.

---

# Intent Graph

The proprietary intelligence model powering TIG.

The Intent Graph combines evidence, signals, weights and playbooks to predict commercial intent.

It is the core intellectual property of the platform.

---

# Playbook Weight Matrix

A configurable mapping that assigns different signal weights to different industries.

Example:

Funding Round

Recruitment:
+15

Marketing:
+35

Insurance:
+10

---

# False Positive

An opportunity that appears valid but does not result in meaningful commercial intent.

False positives should be captured through user feedback to improve future scoring.

---

# Feedback Loop

The continuous process of improving TIG using user outcomes.

Users may indicate:

- Converted
- Useful
- Not Useful
- False Positive

Feedback improves future scoring models while maintaining explainability.

---

# Explainability

The ability to trace every recommendation back to its supporting evidence.

Explainability is a core design principle of TIG.

No recommendation should exist without an evidence chain.

---

# Commercial Intent

The measurable likelihood that a business is preparing to purchase products or services.

Commercial intent is the primary output of TIG.
