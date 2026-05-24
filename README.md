# NCAA D1 Coaching Pipeline

**A four-sport leadership notebook tracking athlete diversification, promotion gaps, and who reaches Division I women's head-coaching roles from 2012 through 2025.**

This project packages a notebook-style leadership brief on the NCAA Division I women's coaching pipeline across women's basketball, softball, volleyball, and soccer. It combines multi-year representation trends, focus-sport comparisons, intervention framing, and women's basketball context to show where athlete diversification outpaced leadership change and where head-coaching access remains structurally constrained.

## How To Use This Template

1. Copy this template into a new repo for your project.
2. Update `project_config.yml` with your project metadata and links.
3. Replace `notebooks/index.html` with your final HTML notebook or dashboard export.
4. Optionally add small datasets to `data/processed/` and list them under `data.expected_files`.
5. Run the setup and checks:

```bash
python scripts/init_project.py
python scripts/validate_data.py
python scripts/publish_check.py
```

## Live Project

- HTML Notebook: https://kbsmd-sportsmusicdata.github.io/ncaa-d1-demographics-coaching-pipeline/
- Portfolio Page: 
- Tableau Public: 

## Project Status

published

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

- NCAA D-I coaching pipeline multiyear panel- Focus-sport trend table- Intervention summary table- Focus-sport comparison table- Women's basketball trend table
## Methodology Summary

See [`docs/methodology.md`](docs/methodology.md).

## Validation Summary

See [`docs/validation_report.md`](docs/validation_report.md).

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

- Decide whether the public repo should remain notebook-first or add a lighter dashboard companion later.
- Reuse the same project structure for another leadership or representation brief.
- Consider branch protection on main once the repo wording and links settle.
