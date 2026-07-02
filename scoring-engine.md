# Scoring Engine

Version

v0.1

---

# Purpose

The Scoring Engine is responsible for transforming business signals into measurable commercial intent.

It is the decision-making engine of TIG Core.

The Scoring Engine never uses generative AI.

Its output must always be deterministic, repeatable and explainable.

---

# Philosophy

Evidence tells us **what happened**.

Patterns tell us **what is changing**.

Signals tell us **what it means**.

The Scoring Engine determines **how important it is**.

---

# Pipeline

```
Evidence

↓

Pattern Engine

↓

Signals

↓

Playbook

↓

Scoring Engine

↓

Intent Score

↓

Opportunity Engine
```

---

# Design Principles

The Scoring Engine must be

- Deterministic
- Explainable
- Configurable
- Versioned
- Testable
- Industry Agnostic

No score should depend on AI.

---

# Score Components

Every Intent Score is calculated from multiple components.

| Component | Purpose |
|------------|---------|
| Signal Weight | Importance of the signal |
| Signal Confidence | Reliability of the signal |
| Source Reliability | Trustworthiness of evidence |
| Pattern Strength | How strong the detected pattern is |
| Freshness | How recent the evidence is |
| Playbook Modifier | Industry-specific adjustment |
| Diversity Bonus | Multiple signal categories |
| Saturation Penalty | Prevent duplicate inflation |

---

# Intent Formula

The exact implementation may evolve.

Conceptually:

```
Intent Score

=

Σ

(
Weight
×

Confidence
×

Freshness
×

Pattern Strength
)

×

Playbook Modifier

−

Penalties

+

Bonuses
```

The formula should remain configurable.

---

# Signal Weight

Each signal has a default weight.

Example

| Signal | Default Weight |
|---------|---------------:|
| Funding Round | 30 |
| Hiring Spike | 25 |
| Office Expansion | 22 |
| Executive Appointment | 18 |
| Website Update | 5 |

Playbooks may override these values.

---

# Confidence

Confidence is inherited from the Signal Engine.

Confidence ranges

0–100

Example

Funding

98%

Website Update

60%

---

# Source Reliability

Source Reliability modifies confidence.

| Grade | Modifier |
|---------|----------|
| A | 1.00 |
| B | 0.90 |
| C | 0.70 |
| D | 0.40 |

Official sources always carry greater influence.

---

# Freshness

Signals decay over time.

Example

```
Funding

180 Days

↓

100%

↓

75%

↓

40%

↓

Expired
```

Each signal defines its own decay curve.

Freshness is configurable.

---

# Pattern Strength

Pattern Strength measures how significant the observed behaviour is.

Example

5 jobs

↓

Weak

10 jobs

↓

Medium

25 jobs

↓

Strong

60 jobs

↓

Exceptional

Pattern strength scales between

0.0

and

1.5

---

# Diversity Bonus

Intent should increase when evidence comes from multiple categories.

Example

Funding

+

Hiring

+

Expansion

↓

Higher confidence than

Funding alone

---

# Saturation Penalty

Repeated evidence should not inflate scores.

Example

100 identical job postings

≠

100× stronger intent.

The engine should detect duplicate or highly similar evidence.

---

# Negative Signals

Some signals reduce intent.

Examples

- Hiring Freeze
- Layoffs
- Office Closure
- Bankruptcy Filing
- Funding Withdrawal

Negative signals subtract from the final score.

---

# Composite Signals

Multiple signals may generate a stronger composite signal.

Example

Funding

+

Hiring Spike

+

Executive Appointment

↓

Growth Momentum

Composite signals have their own weights.

---

# Intent Levels

| Score | Level |
|---------|--------|
| 0–20 | Very Low |
| 21–40 | Low |
| 41–60 | Moderate |
| 61–80 | High |
| 81–100 | Very High |

Playbooks may define different thresholds.

---

# Confidence Levels

| Confidence | Meaning |
|-------------|---------|
| 90–100 | Very High |
| 75–89 | High |
| 60–74 | Medium |
| Below 60 | Low |

---

# Explainability

Every score must expose:

- Contributing Signals
- Signal Weights
- Freshness
- Confidence
- Evidence Chain

Users must never see a score without an explanation.

---

# Versioning

Scoring Models are versioned.

Example

v1

Linear weights

v2

Decay improvements

v3

Composite signals

Historical scores should remain reproducible.

---

# Testing

Every scoring rule must include automated tests.

Tests should verify:

- Weight calculation
- Freshness decay
- Duplicate handling
- Negative signals
- Composite signals
- Explainability

---

# Future Improvements

Future versions may include:

- Bayesian confidence models
- Industry benchmarks
- Historical trend analysis
- Machine learning assisted weighting
- Seasonal adjustments

Any future enhancement must preserve explainability.

---

# Summary

The Scoring Engine converts evidence-backed signals into measurable commercial intent.

It is deterministic, configurable and transparent.

The engine provides the mathematical foundation that powers every opportunity surfaced by TIG.
