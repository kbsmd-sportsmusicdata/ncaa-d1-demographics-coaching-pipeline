# Methodology: NCAA D1 Coaching Pipeline

## Data Sources

### NCAA D-I coaching pipeline multiyear panel

- URL: 
- Notes: Longitudinal table used to track athlete, assistant, and head-coach representation by race group, sport, and year.
### Focus-sport trend table

- URL: 
- Notes: Filtered multi-year view used for the primary four-sport trend framing inside the notebook.
### Intervention summary table

- URL: 
- Notes: Compact summary table used to flag the strongest promotion-gap pressure points by sport and race group.
### Focus-sport comparison table

- URL: 
- Notes: Comparison table that contrasts all-coach and women-only contexts across the four focus sports.
### Women's basketball trend table

- URL: 
- Notes: WBB-specific slice retained so the project can keep a direct basketball lens alongside the four-sport framing.

## Evidence Precedence

The multi-year panel is the base evidence layer for this repo. It carries the year-by-year athlete, assistant-coach, and head-coach representation fields that support the full leadership story.

The other shipped CSVs are review-first slices of that base:

- `coaching_pipeline_focus_trends.csv` keeps the notebook's primary four-sport trend framing compact.
- `coaching_pipeline_intervention_table.csv` surfaces the most decision-relevant gap cases in a short table.
- `coaching_pipeline_comparison_focus_sports.csv` keeps the broad all-coach and women-only comparison in one file.
- `coaching_pipeline_wbb_trends.csv` preserves a direct women's basketball lens for basketball-first readers.

## Cleaning Steps

- Kept the public repo scoped to the notebook-facing evidence tables rather than the full workspace pipeline and raw source files.
- Preserved the 2012-2025 year range and four focus sports used by the published notebook.
- Separated the compact intervention and comparison tables from the longer multi-year panel so the repository stays reviewable.
- Retained a women's basketball-specific trend extract so basketball readers can move from the broad four-sport story into a closer WBB lens.

## Feature Engineering

- Tracked athlete, assistant-coach, and head-coach representation percentages by year, sport, and race group.
- Used promotion-gap and coach-athlete representation gap fields to quantify where leadership access lags the athlete pipeline.
- Included pipeline-strength and hiring-flag fields to support decision-oriented framing rather than descriptive counts alone.

## Selection Logic

This public repo intentionally does not ship the entire WBB Coaching workspace or raw NCAA source archive. The published bundle keeps only the evidence tables that are needed to audit the notebook's core claims:

- the long panel for year-over-year representation context
- the focus-sport trend slice for the main four-sport narrative
- the intervention table for action-oriented summary review
- the comparison table for all-coach versus women-only framing
- the women's basketball trend slice for a direct WBB read

## Metrics

### Primary Metrics

- **Athlete Representation Percentage**: Share of athletes in a given sport-year-race grouping.
  - Interpretation: Higher values indicate stronger athlete presence in the talent pool.
- **Assistant Coach Representation Percentage**: Share of assistant coaches in a given sport-year-race grouping.
  - Interpretation: Higher values indicate stronger representation in the assistant-coach layer.
- **Head Coach Representation Percentage**: Share of head coaches in a given sport-year-race grouping.
  - Interpretation: Higher values indicate stronger representation in the top decision-making role.
- **Promotion Gap**: Difference between assistant-coach representation and head-coach representation.
  - Interpretation: Larger gaps indicate a steeper bottleneck between assistant roles and head-coach roles.

### Derived Metrics

- **Coach-Athlete Representation Gap**: Athlete representation percentage minus coach representation percentage for the relevant layer.
  - Interpretation: Larger positive values indicate leadership representation is lagging the athlete pipeline.
- **Pipeline Strength Score**: Project-specific score built from athlete, assistant, and head-coach representation plus gap signals.
  - Interpretation: Higher values indicate a comparatively healthier leadership pipeline.
- **Hiring Flag**: Project-level categorical flag based on the observed gap profile.
  - Interpretation: Flags the cases where hiring or promotion dynamics warrant closer review.

## Modeling Approach

Not applicable. This project is a descriptive leadership and representation analysis, not a predictive model.

## Validation Checks

- Row count check
- Missing value check
- Duplicate check
- Schema check

## Limitations In The Published Slice

The validation warnings in this repo are driven mostly by sparse promotion-gap and pipeline-strength fields in the source tables, not by failed file generation. Those fields are preserved because the sparsity itself is part of the analytical context, especially in cases where the underlying leadership counts are thin.

## Reproducibility Notes

This project uses a config-driven documentation workflow. Update `project_config.yml`, then regenerate docs using:

```bash
python scripts/generate_docs.py
python scripts/generate_readme.py
```
