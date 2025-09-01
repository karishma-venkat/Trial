# Trial
# ESG → Profitability (2021–2024): Research Methodology & Reproducible Workflow

![Python](https://img.shields.io/badge/Python-3.10%2B-informational)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![License](https://img.shields.io/badge/License-MIT-green)

This repository contains the methodology and reproducible workflow for a study on how ESG relates to firm profitability during 2021–2024, a period marked by post-pandemic recovery, the Ukraine conflict, and EU sustainability regulations.

---

## 📌 Methodology at a Glance (Horizontal Flow)

> GitHub renders Mermaid diagrams automatically.

```mermaid
flowchart LR
  A[**Study Design & Data**<br/>(2021–2024 observational panel,<br/>≈400 firm-years: 100×4)] --> 
  B[**Data Prep & Descriptives**<br/>Clean & merge; summary stats;<br/>missingness & outliers]
  B --> C[**Econometric Analysis**<br/>Fixed-effects (FE) panel regressions;<br/>controls: size, leverage, sector, year FE;<br/>endogeneity checks (lags/IV, robustness)]
  C --> D[**Machine Learning (Prediction)**<br/>Pipelines: Logistic / RF / XGBoost;<br/>CV + tuning; feature importance / SHAP]
  D --> E[**Validation & Synthesis**<br/>Holdout metrics (AUC/acc/R²);<br/>robustness (alt ESG/specs);<br/>triangulate econometrics + ML]
  subgraph Reproducibility
    F["Jupyter workflow: imports → data load → descriptives → FE regressions → ML pipelines → validation<br/><code>DISSERTATION FINAL OUTPUT.ipynb</code> (seeded runs, versioned data/code)"]
  end
  E --> F
