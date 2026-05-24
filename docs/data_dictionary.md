# Data Dictionary: NCAA D1 Coaching Pipeline

## Overview

This document defines key fields used in the project datasets.

## File Map

- `coaching_pipeline_multiyear.csv`: full 2012-2025 representation panel used for year-over-year analysis
- `coaching_pipeline_focus_trends.csv`: compact four-sport trend slice used throughout the notebook
- `coaching_pipeline_intervention_table.csv`: summary table for the strongest promotion-gap pressure points
- `coaching_pipeline_comparison_focus_sports.csv`: all-coach versus women-only comparison table across the focus sports
- `coaching_pipeline_wbb_trends.csv`: women's basketball-specific trend extract

## Field Definitions

| Field | Type | Description | Source | Calculation Logic | Notes |
|---|---|---|---|---|---|
| sport | string | Focus sport label used in the notebook and evidence tables | All shipped CSVs | Source category field | Core grouping field |
| race_group | string | Full race-group label used for representation tracking | All shipped CSVs | Source category field | Use with `race_group_short` for display |
| race_group_short | string | Shortened race-group label for tables and visuals | All shipped CSVs | Derived display label | Presentation-oriented field |
| year | integer | NCAA season year used in the panel and trend tables | Multi-year and trend CSVs | Source year field | Not present in the compact intervention table |
| athlete_race_pct | numeric | Share of athletes in the given sport-year-race grouping | Multi-year and trend CSVs | Athlete count for group divided by athlete total | Talent-pool baseline |
| assistant_pct | numeric | Share of assistant coaches in the given grouping | Multi-year and trend CSVs | Assistant-coach count for group divided by assistant total | Mid-pipeline layer |
| hc_pct | numeric | Share of head coaches in the given grouping | All shipped CSVs | Head-coach count for group divided by head-coach total | Leadership-endpoint layer |
| promotion_gap | numeric | Gap between assistant-coach representation and head-coach representation | Multi-year, trend, and intervention CSVs | `assistant_pct - hc_pct` | Larger values indicate a steeper bottleneck |
| coach_athlete_rep_gap | numeric | Gap between athlete representation and coach representation | Multi-year, trend, and intervention CSVs | Athlete representation minus coach representation | Highlights where leadership lags the athlete pool |
| pipeline_strength_score | numeric | Composite signal used to summarize relative pipeline health | Multi-year, trend, and intervention CSVs | Project-specific combination of representation and gap fields | Sparse in some rows by design |
| hiring_flag | string | Categorical flag summarizing the case's intervention urgency | Multi-year, trend, and intervention CSVs | Project-specific rule-based label | Read with `flag_reason` |
| flag_reason | string | Short explanation for why a row was flagged | Multi-year, trend, and intervention CSVs | Project-specific rule explanation | Useful for fast review |
| significant_gap | boolean | Indicates whether the representation or promotion gap crosses the notebook's alert threshold | Multi-year, trend, and intervention CSVs | Rule-based threshold flag | Supports quick filtering |
| coaching_cut | string | Leadership cut used in the compact intervention summary | Intervention CSV only | Derived summary label | Compact review field |
| asst_pct_all | numeric | Assistant-coach representation in the all-coach comparison view | Comparison CSV only | Comparison-table field | Used alongside women-only fields |
| asst_pct_women | numeric | Assistant-coach representation in the women-only comparison view | Comparison CSV only | Comparison-table field | Used to contrast context shifts |

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
