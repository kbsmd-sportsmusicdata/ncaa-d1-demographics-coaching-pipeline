# Data Dictionary: NCAA D1 Coaching Pipeline

## Overview

This document defines key fields used in the project datasets.

## Field Definitions

| Field | Type | Description | Source | Calculation Logic | Notes |
|---|---|---|---|---|---|
| example_field | string | Example description | Source name | Not applicable | Replace with actual field |

## Primary Metrics

### Athlete Representation Percentage

- Definition: Share of athletes in a given sport-year-race grouping.
- Interpretation: Higher values indicate stronger athlete presence in the talent pool.
### Assistant Coach Representation Percentage

- Definition: Share of assistant coaches in a given sport-year-race grouping.
- Interpretation: Higher values indicate stronger representation in the assistant-coach layer.
### Head Coach Representation Percentage

- Definition: Share of head coaches in a given sport-year-race grouping.
- Interpretation: Higher values indicate stronger representation in the top decision-making role.
### Promotion Gap

- Definition: Difference between assistant-coach representation and head-coach representation.
- Interpretation: Larger gaps indicate a steeper bottleneck between assistant roles and head-coach roles.

## Derived Metrics

### Coach-Athlete Representation Gap

- Formula: Athlete representation percentage minus coach representation percentage for the relevant layer.
- Interpretation: Larger positive values indicate leadership representation is lagging the athlete pipeline.
### Pipeline Strength Score

- Formula: Project-specific score built from athlete, assistant, and head-coach representation plus gap signals.
- Interpretation: Higher values indicate a comparatively healthier leadership pipeline.
### Hiring Flag

- Formula: Project-level categorical flag based on the observed gap profile.
- Interpretation: Flags the cases where hiring or promotion dynamics warrant closer review.
