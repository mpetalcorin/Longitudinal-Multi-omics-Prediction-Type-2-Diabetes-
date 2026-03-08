# Multi-Omics-Prediction-Type-2-Diabetes-
Synthetic, interpretable proof-of-concept for longitudinal multi-omics prediction of incident type 2 diabetes using clinical, polygenic, proteomic, metabolomic, transcript-like, and trajectory features.

# Interpretable Longitudinal Multi-Omics Disease Prediction for Incident Type 2 Diabetes

## Overview

This repository presents a **synthetic proof of concept** for interpretable, longitudinal, multi-omics prediction of **incident type 2 diabetes (T2D)**. The project simulates a cohort with baseline clinical variables, a polygenic risk score, transcript-like features, protein-like features, metabolite-like features, and repeated follow-up measurements. It then uses these data to demonstrate a full predictive modelling workflow, including exploratory analysis, trajectory clustering, unsupervised subtype discovery, cross-validated model comparison, calibration assessment, subgroup robustness analysis, and feature prioritisation.

The work is designed as a **methodological benchmark**, not as a real clinical model. No real patient data are used. Instead, the notebook provides a reproducible scaffold for future deployment on real longitudinal multi-omic cohorts.

## Objectives

The project was designed to address five main questions:

1. Can longitudinal multi-omics improve prediction of future T2D beyond clinical variables alone?
2. Do simulated proteomic and metabolomic signals reproduce expected directional relationships with future disease?
3. Can trajectory features derived from repeated measurements improve risk stratification?
4. Can unsupervised molecular subtypes identify latent states associated with future disease burden?
5. How should predictive performance be interpreted when calibration, subgroup transportability, and feature stability are considered alongside AUROC?

## Repository Contents

- `interpretable_multiomics_t2d_poc_notebook_with_markdown.ipynb`  
  Main notebook containing the full synthetic simulation, modelling workflow, visualisations, and markdown interpretation.

- `simulated_t2d_model_performance.csv`  
  Summary of predictive performance across nested model feature sets.

- `simulated_t2d_univariate_associations.csv`  
  Univariate association analysis for candidate predictors.

- `simulated_t2d_stability_selection.csv`  
  Bootstrap feature-selection stability results.

- `simulated_t2d_permutation_importance.csv`  
  Holdout-set permutation importance results for the best model.

- `simulated_t2d_subgroup_performance.csv`  
  Performance metrics across simulated subgroups.

- `simulated_t2d_risk_deciles.csv`  
  Event rates across model-derived predicted risk deciles.

## Scientific Rationale

Type 2 diabetes develops gradually and is influenced by interacting clinical, genetic, metabolic, inflammatory, and behavioural processes. Prospective human studies have shown that **branched-chain amino acids**, **inflammatory markers**, and selected **circulating proteins** can improve future diabetes prediction, while **longitudinal multi-omics** can reveal trajectories that precede overt disease. This repository uses that general conceptual framework to build a transparent benchmark.

The simulation includes the following qualitative assumptions:

- Higher **HbA1c**, **fasting glucose**, and **body mass index** increase future T2D risk.
- Higher **branched-chain amino acid burden** increases risk.
- Higher **GlycA-like inflammatory signal** increases risk.
- Higher **ACY1-like protein burden** increases risk.
- Higher **adiponectin-like** and **SHBG-like** protein signals are protective.
- A **polygenic risk score** adds modest predictive information.
- Prediction quality can vary across simulated subgroups, illustrating the need for transferability analysis.

## Analysis Workflow

The notebook performs the following steps:

1. Simulates baseline demographics, behaviour, clinical risk factors, latent biological states, and omics features.
2. Simulates repeated measurements at years 0, 2, and 5.
3. Generates incident T2D outcomes using a biologically informed synthetic risk function with censoring.
4. Performs descriptive statistics and exploratory omics analysis.
5. Derives longitudinal slope features and trajectory clusters.
6. Uses principal component analysis to compress omics structure and define unsupervised subtypes.
7. Evaluates nested predictive models using five-fold cross-validation.
8. Compares discrimination, precision-recall performance, calibration, and subgroup robustness.
9. Interprets the best-performing model using sparse coefficients, permutation importance, and bootstrap feature stability.
10. Performs model-based risk stratification and Kaplan-Meier-like event-free survival analysis.

## Main Findings

Because this is a synthetic benchmark, findings should be interpreted as internal proof-of-concept outputs rather than biological claims. Within the simulation:

- Future T2D cases show higher glycaemic, amino acid, inflammatory, and adverse proteomic signals.
- Longitudinal worsening separates future cases from non-cases.
- Unsupervised trajectory clusters and omics subtypes show different future event rates.
- Integrated multi-omics and trajectory-aware models outperform clinical-only models.
- Polygenic information contributes modestly.
- Calibration and subgroup performance remain important, even when discrimination improves.
- Stability-based feature ranking helps distinguish robust predictors from fragile ones.

## Intended Use

This repository is intended for:

- method development,
- teaching and demonstration,
- pipeline benchmarking,
- adaptation to real multi-omic cohorts,
- portfolio or concept-paper support for disease prediction research.

It is not intended for:

- clinical decision-making,
- diagnosis,
- treatment selection,
- public health deployment,
- inference about any real ancestry group or patient population.

## Requirements

Recommended Python environment:

- Python 3.10 or later
- numpy
- pandas
- matplotlib
- scipy
- scikit-learn
- statsmodels, optional

## Running the Notebook

Open the notebook in Jupyter Lab, Jupyter Notebook, or VS Code and run cells from top to bottom. The code is CPU-friendly and does not require a GPU.

## Limitations

This project has several important limitations:

- The dataset is entirely synthetic.
- Effect sizes and joint distributions are simulated rather than estimated from a real cohort.
- The ancestry labels are placeholders for subgroup stress testing only.
- The longitudinal structure is simplified to three visits and mostly linear changes.
- The calibration and performance metrics reflect synthetic rather than clinical realism.

## Future Directions

This framework can be extended by:

- replacing synthetic data with real cohort data,
- using true transcriptomic, proteomic, and metabolomic matrices,
- adding Cox survival models and time-dependent AUC,
- incorporating external validation,
- using missing-data sensitivity analysis,
- comparing additional model classes such as gradient boosting or Bayesian models,
- adding more formal causal prioritisation such as Mendelian randomisation or target-trial emulation.

## Citation

**Petalcorin, M.I.R.** (2026). An interpretable longitudinal multi-omics framework for incident type 2 diabetes prediction. https://github.com/mpetalcorin/Longitudinal-Multi-omics-Prediction-Type-2-Diabetes
