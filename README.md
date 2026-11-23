# MASLD Transcriptomic Machine Learning

### Gene Expression-Based Machine Learning for Metabolic Dysfunction-Associated Steatotic Liver Disease

**Researcher:** Laiba Liaqat  
**Institution:** Forman Christian College University, Lahore  
**Research Area:** Bioinformatics | Transcriptomics | Machine Learning

---

## 1. Project Overview

This repository documents research on the application of transcriptomic data analysis and machine-learning techniques to metabolic dysfunction-associated steatotic liver disease (MASLD).

The project explores gene-expression-based classification, feature selection, model reconstruction, and external evaluation using publicly available datasets from the NCBI Gene Expression Omnibus (GEO).

The repository currently contains a reconstructed 50-gene model artifact, a reviewed research-workflow notebook, and saved external evaluation results.

**Research status:** The repository preserves research findings and model artifacts. The complete historical computational workflow has not been independently verified as reproducible from a clean environment.

## 2. Research Objectives

- Investigate transcriptomic patterns associated with MASLD-related sample classification.
- Integrate and examine gene-expression data from multiple GEO studies.
- Explore gene selection and machine-learning approaches for disease classification.
- Develop and reconstruct gene-expression-based prediction models.
- Evaluate model discrimination and classification performance using external datasets.
- Document model provenance, validation uncertainty, and reproducibility limitations.

## 3. Datasets

The recorded research uses the following GEO datasets:

| Dataset | Role |
|---|---|
| GSE48452 | Model development |
| GSE126848 | Model development |
| GSE135251 | Model development |
| GSE89632 | External evaluation |
| GSE130970 | External sensitivity evaluation |

The original datasets are available through the [NCBI Gene Expression Omnibus](https://www.ncbi.nlm.nih.gov/geo/).

### Recorded Training Dataset Composition

The supplementary research notebook, not currently included in the repository, records:

| Dataset | Samples | Healthy | Disease |
|---|---:|---:|---:|
| GSE48452 | 73 | 41 | 32 |
| GSE126848 | 57 | 26 | 31 |
| GSE135251 | 216 | 10 | 206 |
| **Total** | **346** | **77** | **269** |

The recorded gene-expression analysis includes:

- 10,152 common genes.
- 3,164 direction-consistent genes.
- A selected 50-gene feature panel.
- Within-sample percentile-rank feature processing.

These figures reflect saved notebook outputs rather than an independently rerun analysis.

## 4. Machine-Learning Methodology

The supplementary model reproduction experiment records the following configuration:

| Parameter | Configuration |
|---|---|
| Algorithm | Logistic Regression |
| Selected features | 50 genes |
| Feature standardization | StandardScaler |
| Regularization | C = 0.1 |
| Solver | lbfgs |
| Maximum iterations | 3000 |
| Random state | 42 |
| Sample weighting | Normalized inverse-frequency weights |

The research additionally documents model development, cross-study analysis, and reconstruction investigations.

### Published Model Artifact

The repository contains:

`MASLD_50gene_REPRODUCED_20261119_162522 (1).joblib`

This artifact represents a reproduced 50-gene model recorded during the research workflow.

The supplementary reproduction notebook reports agreement with a reconstructed V3 model in selected features, scaler parameters, coefficients, and intercept.

However, the reproduced model should not automatically be considered equivalent to the original historical model, and the external evaluation results below should not be attributed to this particular artifact without confirming model provenance.

## 5. External Evaluation

The repository contains external evaluation outputs for two GEO datasets.

### Performance Summary

| Dataset | Samples | ROC-AUC | Sensitivity | Specificity |
|---|---:|---:|---:|---:|
| GSE89632 | 63 | 0.9615 | 64.10% | 100.00% |
| GSE130970 | 74 | 0.9750 | 74.29% | 100.00% |

### Reported 95% Confidence Intervals

| Dataset | ROC-AUC 95% CI | Sensitivity 95% CI | Specificity 95% CI |
|---|---|---|---|
| GSE89632 | 0.9017–1.0000 | 47.18%–78.80% | 85.75%–100.00% |
| GSE130970 | 0.9321–1.0000 | 62.44%–83.99% | 39.76%–100.00% |

These results are reported in `External_Validation_95CI_Results.csv`.

**Interpretation:** The reported ROC-AUC values indicate strong discrimination in the evaluated samples, although classification sensitivity is lower than specificity.

The confidence intervals, especially the wide specificity interval for GSE130970, indicate uncertainty that must be considered when interpreting the results.

These evaluations do not establish prospective clinical performance or diagnostic suitability.

The exact model version and evaluation protocol associated with the reported metrics should be independently verified.

## 6. Repository Structure

The repository currently contains the following files:

```text
MASLD-Transcriptomic-ML/
│
├── External_Validation_95CI_Results.csv
│
├── GSE130970_sensitivity_predictions.csv
│
├── GSE89632_fresh_predictions.csv
│
├── MASLD_50gene_REPRODUCED_20261119_162522 (1).joblib
│
├── MASLD_Research_Workflow_Reviewed.ipynb
│
└── README.md
```

`README.md` is shown as the documentation file to be added; it was not present in the supplied repository listing.

### File Descriptions

**External_Validation_95CI_Results.csv**

Contains reported external evaluation metrics and 95% confidence intervals.

**GSE89632_fresh_predictions.csv**

Contains sample-level binary prediction results for 63 evaluated samples from GSE89632.

**GSE130970_sensitivity_predictions.csv**

Contains sample-level prediction results for 74 evaluated samples from GSE130970.

**MASLD_50gene_REPRODUCED_20261119_162522 (1).joblib**

Contains a serialized reconstructed machine-learning model artifact.

**MASLD_Research_Workflow_Reviewed.ipynb**

Preserves the chronological research workflow, including preprocessing, model experiments, validation investigations, and reconstruction work.

## 7. Research Workflow Notebook

The reviewed notebook records the historical research process and related experiments, including:

1. Project setup and data acquisition.
2. Gene-expression data preprocessing.
3. Sample harmonization and label preparation.
4. Gene-selection experiments.
5. Machine-learning model training and evaluation.
6. Cross-study and external validation investigations.
7. Model artifact inspection and reconstruction.
8. Reproducibility and provenance investigations.

**Important:** The reviewed notebook is a research archive, not a verified standalone execution pipeline. Some incomplete historical code was disabled, and external files may be necessary to execute particular experiments.

## 8. Reproducibility

The available repository files document research outputs but do not currently provide a fully verified, end-to-end reproduction environment.

To reproduce the experiments, additional components may be required, including:

- Original GEO expression matrices and metadata.
- Verified preprocessing and validation scripts.
- Exact selected gene lists and feature order.
- Model configuration and classification thresholds.
- Compatible Python and package versions.
- Experiment-specific model artifacts.

A verified dependency file and complete execution instructions should be added after the computational environment has been audited.

**Security:** Only load `.joblib` files from trusted sources, because serialized Python model files may execute code during loading.

## 9. Model Provenance

The research history distinguishes historical models, reconstructed models, and candidate artifacts.

A reconstructed V4 candidate is mentioned in the research archive, but the original frozen V4 model was not recovered.

The V4 candidate must not be represented as externally validated using the published evaluation results without a separate verified evaluation.

## 10. Research Limitations

- External evaluation was performed on limited sample counts.
- Reported confidence intervals indicate uncertainty in some metrics.
- Results may depend on study-level differences in samples, assays, and preprocessing.
- The published model artifact has not been independently linked to all reported evaluation outputs.
- The complete historical computational workflow is not presently verified as reproducible from this repository alone.
- Clinical diagnostic performance has not been established.

## 11. Data Availability

The public expression datasets are available through the NCBI GEO database:

- [GSE48452](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE48452)
- [GSE126848](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE126848)
- [GSE135251](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE135251)
- [GSE89632](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE89632)
- [GSE130970](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE130970)

Original dataset publications should be cited when using the data for subsequent research.

## 12. Intended Use

This repository is intended for academic, educational, and research purposes only.

It is not a clinically validated diagnostic system or medical device.

## 13. Researcher

**Laiba Liaqat**  
Forman Christian College University, Lahore

**GitHub:** [laibaliaqat87-prog](https://github.com/laibaliaqat87-prog)

## 14. Acknowledgements

This research uses publicly available transcriptomic datasets provided by researchers through the NCBI Gene Expression Omnibus.

Acknowledgement is given to the original investigators and institutions responsible for generating and publishing the datasets.

---

**Documentation note:** Reported metrics and model details are based on existing research outputs and available notebook records. The repository should be regarded as a documented research archive until end-to-end reproduction and model-specific external validation have been independently verified.
