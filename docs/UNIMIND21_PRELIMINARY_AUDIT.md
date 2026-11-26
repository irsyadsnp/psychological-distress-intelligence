# UniMind-21 Preliminary Dataset Audit

**Project:** Psychological Distress Intelligence  
**Audit stage:** 01B — preliminary source and metadata inspection  
**Audit date:** 2026-11-26  
**Status:** Pending direct file-level validation

## 1. Source identification

- Dataset: UniMind-21
- Repository: Zenodo
- DOI: https://doi.org/10.5281/zenodo.21803693
- Record: https://zenodo.org/records/21803693
- Contributors listed in the NLM Dataset Catalog: Md Tanvir Islam, H. M. Nahid Kawsar, and Tanjina Sultana
- Reported publication date: 2026-08-05
- Reported license: Creative Commons Attribution 4.0 International (CC BY 4.0)

## 2. Metadata reported by the catalog

The NLM Dataset Catalog describes the dataset as containing 633 undergraduate and graduate students from public universities in Bangladesh.

Two data files are described:

1. Raw dataset: 39 columns, comprising 18 contextual features and 21 DASS-21 item responses.
2. Processed dataset: 21 columns, comprising 18 contextual features and three binary outcomes for depression, anxiety, and stress.

The catalog reports that the processed outcomes were derived from DASS-21 subscale scoring, mapped to severity levels, and then dichotomized as Moderate-or-higher versus Normal/Mild. The catalog also reports ethics approval from the Research and Innovation Centre, Khulna University (reference KUECC-2025-11-162).

These statements are transcribed as source metadata, not independently verified against the dataset files or ethics documentation.

## 3. Preliminary suitability assessment

**Potential strengths**
- The described raw file includes item-level DASS-21 responses, allowing independent recomputation of subscale scores.
- The 18 contextual variables may support analyses of associations between contextual factors and self-reported distress.
- The reported CC BY 4.0 license is potentially compatible with reuse subject to attribution and license terms.

**Important limitations**
- The sample is limited to students at public universities in Bangladesh. Findings should not be generalized to all adults, all students, or Indonesia.
- A sample size of 633 may be adequate for some descriptive and regression analyses, but does not automatically justify complex predictive modeling or extensive subgroup analysis.
- Binary labels derived from DASS-21 scores are screening-style classifications, not clinical diagnoses.
- The processed labels are derived from the same 21 questionnaire items. Using those items to predict their own derived labels would create target leakage.
- The existence of ethics approval in catalog metadata does not establish that every proposed secondary use is covered by the original consent or ethics approval.

## 4. Direct file inspection still required

The dataset is **not approved for analysis yet**. The following checks must be completed after obtaining the actual archive and documentation:

- Record exact filenames, file sizes, version, and checksums.
- Inspect the data dictionary and definitions for all 18 contextual variables.
- Confirm the 21 item names, item order, response coding, and language/version of the instrument.
- Recompute depression, anxiety, and stress subscale scores from the raw items.
- Verify any multiplication-by-two convention and the severity cutoffs used.
- Reproduce the three binary labels and quantify disagreements with the processed file.
- Inspect missingness, duplicate rows, invalid values, impossible combinations, and outliers.
- Determine whether repeated observations, clustering by university, or sampling weights exist.
- Review the license text, consent information, and ethics documentation from the original record.

## 5. Modeling decision

No predictive model will be trained until the raw data and variable documentation pass the checks above.

If suitable contextual variables are available, a model may use those variables as predictors and independently recomputed DASS-21 outcomes as targets. Evaluation must use a defensible validation strategy and report class prevalence, uncertainty, calibration, and subgroup limitations. SHAP explanations will be interpreted as model attributions, not causal effects.

If the contextual variables are insufficiently documented or the data structure does not support robust validation, the project will remain focused on descriptive, psychometric, and inferential analyses.

## 6. Current decision

**Decision: retain UniMind-21 as the leading candidate, but do not yet approve it as the analysis dataset.**

The current evidence supports only a metadata-level screening. Direct inspection of the downloadable files is a required gate before Stage 01 can be closed.

## 7. Sources

- UniMind-21 record: https://doi.org/10.5281/zenodo.21803693
- NLM Dataset Catalog entry: https://datasetcatalog.nlm.nih.gov/dataset?q=0003231007

