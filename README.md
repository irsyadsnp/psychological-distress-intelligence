# Psychological Distress Intelligence

A reproducible research project examining self-reported psychological distress using statistical analysis, psychometrics, and—only where methodologically justified—machine learning and explainable AI.

## Research scope

The initial focus is the Depression Anxiety Stress Scales (DASS-21). DASS-21 is a self-report measure of symptom severity; it is not, by itself, a clinical diagnosis.

The research protocol defines the research questions, scoring safeguards, analysis plan, dataset-selection criteria, and data-governance requirements.

## Current status

**Stage:** Repository setup  
**Protocol:** Draft v0.1.0  
**Dataset:** Not yet selected or verified  
**Analysis:** Not started

No dataset will be treated as suitable until its source, license, instrument version, scoring, sampling structure, privacy conditions, and research suitability have been checked.

## Methodological safeguards

- Do not interpret DASS-21 scores as clinical diagnoses.
- Do not predict a score or category from the same questionnaire items used to calculate that target; this creates target leakage.
- Use machine learning only when independent predictors and a defensible prediction question exist.
- Treat SHAP values as model explanations, not causal effects.
- Keep identifiable, restricted, or non-redistributable raw data out of this public repository.
- Document preprocessing, exclusions, assumptions, uncertainty, and limitations.

## Repository structure

```text
.github/workflows/   Continuous-integration workflows
data/raw/            Original data; local/private unless redistribution is permitted
data/interim/        Intermediate data products
data/processed/      Analysis-ready data products
docs/                Research protocol and documentation
notebooks/           Exploratory and reproducible notebooks
src/                 Reusable analysis code
tests/               Automated tests
reports/figures/     Generated figures for reports
CITATION.cff         Software citation metadata
```

## Research protocol

See [docs/RESEARCH_PROTOCOL.md](docs/RESEARCH_PROTOCOL.md) for the research protocol and [docs/DATASET_SCREENING.md](docs/DATASET_SCREENING.md) for the candidate dataset assessment.

## Reproducibility and data policy

The repository is public. Do not upload personal health information, direct identifiers, restricted datasets, or data whose license does not permit redistribution. When raw data cannot legally or ethically be shared, document its provenance and provide reproducible acquisition instructions where permitted.

Dependencies, environment configuration, and analysis code will be added after the dataset and analysis workflow have been verified.

## License

This project is released under the MIT License. This license applies to the repository's code and documentation; it does not grant rights to third-party datasets or instruments.
