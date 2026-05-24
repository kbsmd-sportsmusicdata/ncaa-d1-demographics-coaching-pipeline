# Project Handoff: NCAA D1 Coaching Pipeline

## Current Status

in-progress

## Project Purpose

This project packages a notebook-style leadership brief on the NCAA Division I women's coaching pipeline across women's basketball, softball, volleyball, and soccer. It combines multi-year representation trends, focus-sport comparisons, intervention framing, and women's basketball context to show where athlete diversification outpaced leadership change and where head-coaching access remains structurally constrained.

## Key Deliverables

- Primary deliverable: HTML notebook
- Notebook: `notebooks/index.html`
- Executive summary: `docs/executive_summary.md`
- Methodology: `docs/methodology.md`
- Data dictionary: `docs/data_dictionary.md`
- Validation report: `docs/validation_report.md`

## Important Scripts

- `scripts/init_project.py`
- `scripts/generate_docs.py`
- `scripts/generate_readme.py`
- `scripts/validate_data.py`
- `scripts/publish_check.py`

## Known Limitations

- This repo ships reviewable evidence tables, not the full coaching-workspace build chain or raw NCAA source archive.
- The notebook centers four focus sports, so readers should not treat it as a complete census of every NCAA Division I women's sport.
- Pipeline and hiring flags are decision-support framing tools, not causal estimates of why a leadership gap exists.

## Next Steps

- Publish the notebook through GitHub Pages and backfill the live URL into this config.
- Decide whether the public repo should remain notebook-first or add a lighter dashboard companion later.
- Reuse the same project structure for another leadership or representation brief once this repo is live.

## Deployment Notes

GitHub Pages should deploy `notebooks/index.html` through the workflow in `.github/workflows/deploy_pages.yml`.
