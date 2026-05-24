# NCAA D1 Coaching Pipeline

**A four-sport leadership notebook tracking athlete diversification, promotion gaps, and who reaches Division I women's head-coaching roles from 2012 through 2025.**

This project packages a notebook-style leadership brief on the NCAA Division I women's coaching pipeline across women's basketball, softball, volleyball, and soccer. It combines multi-year representation trends, focus-sport comparisons, intervention framing, and women's basketball context to show where athlete diversification outpaced leadership change and where head-coaching access remains structurally constrained.

## How To Use This Repo

1. Start with `notebooks/index.html` to read the full coaching-pipeline story in notebook form.
2. Use the evidence tables in `data/processed/` to inspect the multi-year panel, focus-sport comparisons, intervention framing, and women's basketball-specific context behind the notebook.
3. Regenerate the docs and rerun the checks after any data or wording update:

```bash
python scripts/init_project.py
python scripts/validate_data.py
python scripts/publish_check.py
```

## Live Project

- HTML Notebook: Pending GitHub Pages deployment
- Portfolio Page: Not published yet
- Tableau Public: Not used for this project

## Project Status

in-progress

## Why This Project Matters

Athlete diversification in NCAA Division I women's sports accelerated over the last decade, but leadership diversification did not keep pace. This project separates athlete representation, assistant-coach representation, and head-coach access so reviewers can see where the promotion bottleneck is most persistent and which sports show the widest leadership gaps.

## Key Questions

- Where did athlete diversification outpace leadership diversification from 2012 through 2025?
- Which sports show the largest gap between assistant-coach representation and head-coach representation?
- How different does the coaching pipeline look when women's basketball is viewed alongside softball, volleyball, and soccer?

## Audience

- athletic department leaders
- coaching staff and operations leaders
- sports analytics portfolio reviewers

## Project Outputs

- Primary deliverable: HTML notebook
- Notebook path: `notebooks/index.html`
- Report path: `docs/executive_summary.md`

## Data Sources

- NCAA D-I coaching pipeline multiyear panel
- Focus-sport trend table
- Intervention summary table
- Focus-sport comparison table
- Women's basketball trend table

## Methodology Summary

See [`docs/methodology.md`](docs/methodology.md).

## Validation Summary

See [`docs/validation_report.md`](docs/validation_report.md). Current warnings reflect expected sparsity in promotion-gap and pipeline-strength fields rather than missing files or broken repo setup.

## Data Dictionary

See [`docs/data_dictionary.md`](docs/data_dictionary.md).

## Repo Structure

```text
/data
/docs
/notebooks
/reports
/scripts
/sql
/templates
```

## How To Run

```bash
pip install -r requirements.txt
python scripts/generate_docs.py
python scripts/validate_data.py
python scripts/generate_readme.py
```

## Next Steps

- Publish the notebook through GitHub Pages and backfill the live URL into this config.
- Decide whether the public repo should remain notebook-first or add a lighter dashboard companion later.
- Reuse the same project structure for another leadership or representation brief once this repo is live.
