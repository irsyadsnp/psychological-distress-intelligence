# Dataset Screening — Stage 01

**Status:** Preliminary screening; no dataset approved for analysis  
**Version:** 0.1.0  
**Review date:** 2026-11-26

## 1. Screening objective

Identify a legally reusable, methodologically suitable DASS-21 dataset for reproducible statistical and psychometric analysis. Machine learning is conditional on the availability of predictors independent of the DASS-21 items used to derive the outcome.

This document records repository-level metadata only. A dataset is not approved until its downloadable files, codebook, item coding, study documentation, and license are inspected directly.

## 2. Candidate comparison

| Candidate | Population / sample | Publicly described contents | License / access | Preliminary assessment |
|---|---|---|---|---|
| UniMind-21 (Zenodo, DOI: 10.5281/zenodo.21803693) | 633 undergraduate and graduate students at public universities in Bangladesh | Raw file described as 18 contextual features plus 21 DASS-21 item responses (39 columns); processed file described as 18 contextual features plus three binary D/A/S labels | CC BY 4.0, according to NLM Dataset Catalog | **Priority candidate for technical inspection.** Has contextual predictors independent in principle from DASS items, but sample size, label imbalance, variable definitions, consent/ethics documentation, and scoring must be checked. The processed labels must be independently reproduced from raw items. |
| Indonesian DASS-21 and ERS dataset (Mendeley Data, DOI: 10.17632/sk27t97ymb.1) | Indonesia; 746 DASS-21 records and 438 ERS records | Three DASS subscales, three ERS subscales, and demographic data are described; item-level availability is not established by the landing-page description | CC BY 4.0 | **High contextual relevance, pending file inspection.** Potentially useful for descriptive and association analyses. Not yet suitable for psychometric item-level work or prediction until exact columns and record overlap are known. |
| DASS-21 early-pregnancy study — public reproducibility record (Zenodo, DOI: 10.5281/zenodo.21435634) | 438 first-trimester pregnant women in Makassar, Indonesia | Public aggregate tables, scoring map, questionnaire as administered, analysis specification, and code; no participant-level records | Public materials CC BY 4.0; participant-level data are separately restricted | **Useful for replication and local methodological context, not individual-level ML.** Do not attempt to infer or reconstruct participant rows from aggregate tables. |
| Psychosocial risk factors and DASS-21 levels among university students in Bangladesh (Mendeley Data, DOI: 10.17632/6m2bgsd8sf.2) | Tertiary-level students in Bangladesh; exact N not established from landing-page metadata reviewed | Demographics, psychosocial risk factors, and DASS-21-derived depression, anxiety, stress measures | CC BY 4.0; de-identified according to description | **Secondary candidate.** Need exact sample size, raw-item availability, codebook, and whether outcomes are continuous or categorical. Avoid outcome leakage if only DASS-derived labels are supplied. |
| Mental Health dataset based on DASS-21 (Mendeley Data, record br82d4xkj7) | Population details need further verification | Landing-page catalog description documents demographic variables and 21 questionnaire items, with 0–3 response coding and item grouping | CC BY 4.0 according to NLM Dataset Catalog | **Potential item-level candidate.** Need inspect original record, sample size, instrument language/version, codebook, and study provenance before use. |

## 3. Preliminary recommendation

Proceed with **UniMind-21 as the first technical-inspection candidate**, not as an approved final dataset.

Reason:
- Its public catalog description explicitly identifies 633 student respondents.
- The raw file is described as containing all 21 DASS-21 items and 18 contextual features.
- The contextual features could support a non-circular prediction question if they are genuinely measured independently of DASS responses.
- The described CC BY 4.0 license is compatible with reuse subject to attribution, but the exact record license and file-level terms must still be confirmed before redistribution.

Important limitations:
- N=633 is modest for flexible machine learning and may be inadequate for some subgroup or factor-analytic claims.
- A binary threshold of moderate-or-higher versus normal/mild discards ordinal information and requires justification.
- Class imbalance may make accuracy misleading; report class prevalence and use balanced metrics.
- The processed target labels must be recomputed from raw item responses and checked against the supplied labels.
- A model must not use DASS-21 items, subscale sums, severity categories, or transformations of these as predictors when predicting a target derived from those same items.
- SHAP describes model behavior, not causal effects or clinical mechanisms.

## 4. Required verification before approval

### Provenance and governance
- [ ] Open the canonical repository record and confirm authors, publication date, version, DOI, and institutional provenance.
- [ ] Read the study paper or protocol and verify recruitment, inclusion criteria, sampling method, and data-collection period.
- [ ] Confirm ethics approval and consent language for secondary research and public redistribution.
- [ ] Confirm the dataset license on the source record and any separate file-level conditions.
- [ ] Confirm that no direct identifiers or high-risk quasi-identifiers are present.

### Instrument and scoring
- [ ] Confirm the exact DASS-21 version, language, and item wording.
- [ ] Confirm response coding and direction; do not assume 0–3 without checking the source.
- [ ] Confirm item-to-subscale mapping from authoritative documentation.
- [ ] Recompute each subscale from the 21 raw items.
- [ ] Confirm whether scores are multiplied by two for comparison with DASS-42 severity bands.
- [ ] Reproduce the provided processed labels and document any discrepancies.

### Data integrity and analytical suitability
- [ ] Inspect dimensions, variable names, types, value ranges, and missingness.
- [ ] Check exact and near-duplicate records, including possible repeated respondents.
- [ ] Inspect impossible values, inconsistent coding, and outliers.
- [ ] Examine class distribution and subgroup sizes.
- [ ] Identify whether contextual predictors are independent of the DASS-21 outcomes.
- [ ] Decide whether the data support descriptive, psychometric, association, or predictive analyses separately.

## 5. Analysis decision rules

1. If raw item-level responses are available and valid, prioritize scoring verification, item distributions, reliability, and psychometric structure.
2. If contextual predictors are independently measured, assess a prediction task with a predeclared target and leakage audit.
3. Use stratified validation only when observations are independent. If repeated observations or clusters exist, use group-aware splits.
4. Compare simple baselines before complex models. Use nested validation or a held-out test set where sample size permits.
5. Report uncertainty, calibration, class-specific performance, and limitations; do not rely on accuracy alone.
6. If only derived subscale scores or aggregate tables are available, restrict the research questions accordingly. Do not claim item-level psychometric validation or individual-level prediction.

## 6. Source records

- UniMind-21, NLM Dataset Catalog: https://datasetcatalog.nlm.nih.gov/dataset?q=0003231007
- Indonesian DASS-21 and ERS dataset, Mendeley Data: https://data.mendeley.com/datasets/sk27t97ymb/1
- Early-pregnancy DASS-21 public reproducibility materials, Zenodo: https://zenodo.org/records/21435634
- Psychosocial risk factors and DASS-21 dataset, Mendeley Data: https://data.mendeley.com/datasets/6m2bgsd8sf/2
- Mental Health dataset based on DASS-21, Mendeley Data: https://data.mendeley.com/datasets/br82d4xkj7

## 7. Current decision

**No dataset is approved yet.** UniMind-21 is the first candidate for file-level inspection. The Indonesian Mendeley dataset is retained as a contextually relevant alternative. No dataset files have been copied into this public GitHub repository.

Next action: obtain and inspect the UniMind-21 files and documentation, then update this report with verified schema, scoring, integrity, and governance findings.
