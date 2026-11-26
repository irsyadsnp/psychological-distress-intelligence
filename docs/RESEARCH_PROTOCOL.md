# Research Protocol

## Project

**Title:** Psychological Distress Intelligence  
**Subtitle:** A Statistical and Explainable Machine Learning Study of Depression, Anxiety, and Stress  
**Repository:** `irsyadsnp/psychological-distress-intelligence`  
**Protocol status:** Draft — dataset not yet selected or verified  
**Protocol version:** 0.1.0

## 1. Background and scope

This project will examine self-reported symptoms of depression, anxiety, and stress using the 21-item Depression Anxiety Stress Scales (DASS-21), subject to verification of the dataset, instrument version, language, sampling procedure, and usage permissions.

DASS-21 is a self-report measure of symptom severity. It is not, by itself, a diagnostic instrument. Project outputs must not be presented as clinical diagnoses, individual risk determinations, or substitutes for professional assessment.

## 2. Research objectives

1. Describe the distributions of depression, anxiety, and stress scores in the verified study sample.
2. Examine associations among the three DASS-21 subscale scores.
3. Explore differences in scores across available demographic or contextual characteristics, where sample sizes and measurement quality permit.
4. Evaluate the psychometric properties that can validly be assessed from the available item-level data.
5. Assess whether independent, non-overlapping contextual variables provide useful out-of-sample information about DASS-21 outcomes.
6. Explain model behavior and document limitations, uncertainty, and potential sources of bias.

## 3. Research questions

- **RQ1:** What are the distributions of depression, anxiety, and stress scores in the study sample?
- **RQ2:** What associations are observed among the three DASS-21 subscales?
- **RQ3:** Do DASS-21 scores differ across available demographic or contextual groups?
- **RQ4:** What evidence supports the reliability and factor structure of the instrument in this dataset?
- **RQ5:** If suitable independent predictors are available, how well can models estimate or classify DASS-21 outcomes on held-out data?
- **RQ6:** Which independent predictors contribute to model predictions, and how stable are those explanations?

## 4. Measurement and scoring plan

The dataset must be checked against the correct DASS-21 item wording, response options, item order, language version, and scoring key before scores are calculated.

The standard DASS-21 contains 21 items, with seven items assigned to each subscale:

- Depression
- Anxiety
- Stress

Responses are commonly coded from 0 to 3. The seven item responses for each subscale are summed. Multiplication by two is used when comparing DASS-21 scores with the severity labels or norms defined for the full DASS-42 scale. The exact scoring convention and cut-offs will be documented with an authoritative instrument reference before implementation.

No scoring assumptions will be applied to a dataset until its coding and instrument version have been verified. Missing-item handling will follow a documented rule supported by the instrument guidance or a justified analysis plan; missing values will not be silently imputed.

## 5. Statistical analysis plan

Subject to data suitability:

1. Data structure, provenance, and codebook review.
2. Data-quality assessment: missingness, duplicate records, invalid values, response patterns, and possible repeated/grouped observations.
3. Descriptive statistics and visual exploration.
4. Subscale scoring and distribution checks.
5. Internal consistency estimates, with appropriate caveats; coefficient alpha will not be treated as proof of unidimensionality.
6. Factor analysis only if sample size, item coding, response distributions, and sampling assumptions support it. Ordinal-item methods will be considered where appropriate.
7. Correlation and group-comparison analyses selected according to measurement level and distributional assumptions.
8. Effect sizes and confidence intervals alongside p-values; multiple-testing adjustments where relevant.

All statistical assumptions, exclusions, transformations, and deviations from this plan will be recorded.

## 6. Predictive modeling safeguards

Predictive modeling is conditional on the verified dataset containing suitable predictors that are independent of the target construction.

**Target leakage is prohibited.** DASS-21 item responses, subscale sums, or transformations of those same items must not be used as predictors when the target is a score or severity category derived from those items. Such a model would merely reconstruct the scoring rule and would not demonstrate meaningful prediction.

If only DASS-21 items and derived scores are available, the project will prioritize psychometric and statistical analysis rather than force a machine-learning task. If independent contextual predictors are available, candidate models may include regularized regression, random forest, and gradient boosting, with a transparent baseline.

Validation will account for repeated observations or grouped participants if present. Preprocessing and feature selection must be fitted within each training fold. Evaluation will use suitable held-out or cross-validation procedures and metrics appropriate to the target. Calibration, class imbalance, uncertainty, and subgroup performance will be assessed where feasible.

SHAP or other explainability methods will be used only after model validity and evaluation are established. Feature attribution will be interpreted as model behavior, not causal effect or psychological mechanism.

## 7. Data governance and reproducibility

- Record the dataset title, authors, source URL, version, access date, license, and citation.
- Verify that the license permits the intended analysis and any redistribution.
- Do not commit identifiable, sensitive, or restricted participant-level data to this public repository.
- Keep raw data outside version control unless redistribution is explicitly permitted and privacy review supports it.
- Provide reproducible instructions, environment specifications, random seeds where applicable, and data-preparation scripts.
- Preserve an audit trail of data exclusions, transformations, and analysis decisions.
- Do not infer clinical diagnoses or make individual-level treatment recommendations.

## 8. Limitations to assess

Potential limitations include non-probability sampling, self-selection, self-report measurement error, cross-sectional design, cultural and language differences, unmeasured confounding, small subgroup sizes, class imbalance, and limited external validity. The final report will distinguish observed associations from causal claims.

## 9. Dataset decision gate

The dataset will not be approved for analysis until the following are documented:

- Source and provenance are identifiable.
- License and permitted use are clear.
- Instrument version and language are known.
- Item coding and scoring key can be verified.
- Relevant variables and sample structure are understood.
- Privacy and disclosure risks are acceptable.
- The dataset supports the proposed research questions.

If these conditions are not met, the dataset will be rejected or the research scope will be revised.

## 10. Planned project stages

1. Repository setup and research specification.
2. Dataset acquisition and provenance verification.
3. Data-quality audit.
4. DASS-21 scoring.
5. Psychometric analysis.
6. Exploratory data analysis.
7. Statistical inference.
8. Predictive modeling, only if justified.
9. Model evaluation.
10. Explainability, only if justified.
11. Research report and final repository audit.

## 11. References to verify before analysis

The final implementation must cite the authoritative DASS manual or scoring guidance applicable to the exact instrument version and language used, as well as the dataset's original publication or documentation. References will be added after the dataset is selected and verified.
