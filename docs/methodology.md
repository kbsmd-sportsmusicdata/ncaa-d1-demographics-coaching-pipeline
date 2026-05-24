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

## Cleaning Steps

- Kept the public repo scoped to the notebook-facing evidence tables rather than the full workspace pipeline and raw source files.
- Preserved the 2012-2025 year range and four focus sports used by the published notebook.
- Separated the compact intervention and comparison tables from the longer multi-year panel so the repository stays reviewable.
- Retained a women's basketball-specific trend extract so basketball readers can move from the broad four-sport story into a closer WBB lens.

## Feature Engineering

- Tracked athlete, assistant-coach, and head-coach representation percentages by year, sport, and race group.
- Used promotion-gap and coach-athlete representation gap fields to quantify where leadership access lags the athlete pipeline.
- Included pipeline-strength and hiring-flag fields to support decision-oriented framing rather than descriptive counts alone.

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

## Reproducibility Notes

This project uses a config-driven documentation workflow. Update `project_config.yml`, then regenerate docs using:

```bash
python scripts/generate_docs.py
python scripts/generate_readme.py
```
