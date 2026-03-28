# AI-Based Prediction of 12-Month Survival in Liver Graft Recipients

> ⚠️ **Code and Data Availability (Under Editorial Review)**  
> This repository documents the computational framework associated with a manuscript currently **under editorial review** at the *Computational and Structural Biotechnology Journal (CSBJ)*.  
>  
> **In the event that the manuscript is accepted for publication**, the complete source code and a carefully curated, fully anonymized reproducibility dataset will be made publicly available in this repository, together with data dictionaries, preprocessing descriptions, and versioning information sufficient to enable independent replication of the reported results.

---

This repository accompanies the manuscript:

**A Study on the Use of Artificial Intelligence in Predicting the Life Expectancy of Liver Graft Recipients**  
(under editorial review at *Computational and Structural Biotechnology Journal*).

The study investigates the application of artificial intelligence (AI) and machine-learning models to predict **12-month post-transplant survival** in liver graft recipients, using clinical variables routinely available at the time of organ donation and graft acceptance.

The primary purpose of this repository is to provide **methodological and computational transparency**. The models described are intended for research and reproducibility purposes and are **not** designed for direct clinical deployment.

---

## Scientific Background

Liver transplantation is a life-saving intervention performed under conditions of severe organ scarcity and time-critical decision-making. Although advances in surgical techniques, immunosuppression, and perioperative care have improved outcomes, mortality within the first year after transplantation remains clinically relevant.

The **Model for End-Stage Liver Disease (MELD)** score is widely used to prioritize candidates on transplant waiting lists based on pre-transplant mortality risk. However, MELD was not designed to estimate post-transplant survival and does not explicitly incorporate many donor-related, graft-related, and logistical factors that influence graft acceptance decisions.

In real-world practice, graft acceptance relies on a complex combination of objective variables and expert clinical judgment, introducing unavoidable subjectivity. This work evaluates whether AI-based models trained on historical registry data can provide **complementary, data-driven estimates of post-transplant outcomes**, supporting further scientific investigation of donor–recipient matching.

---

## Objectives

- Develop machine-learning models to predict **12-month survival after liver transplantation**.
- Compare classical statistical approaches with modern AI-based methods under a unified evaluation protocol.
- Explore **UMAP-based dimensionality reduction** for structural pattern analysis in high-dimensional transplant data.
- Provide a reproducible computational framework aligned with CSBJ and Elsevier standards.

---

## Dataset Summary

- **Source:** São Paulo State liver-transplant registry  
- **Custodian:** São Paulo State Department of Health (Secretaria de Estado da Saúde de São Paulo)  
- **Study period:** 2007–2022  
- **Final cohort:** 7,098 donor–recipient pairs  
- **Features:** 77 donor-, recipient-, graft-, and logistics-related variables  
- **Outcome:** Survival ≥ 12 months vs. < 12 months post-transplant  

All data were provided to the investigators in **fully anonymized form**, in compliance with Brazil’s General Data Protection Law (LGPD), under the terms set by the data custodian and with approval of the appropriate Research Ethics Committee.

---

## Computational Methods

### Supervised Models
- Logistic Regression  
- Random Forest  
- Gradient Boosting  
- XGBoost  
- Support Vector Machine (SVM)  

### Dimensionality Reduction
- **UMAP (Uniform Manifold Approximation and Projection)**
- **PCA (Principal Component Analysis)**

  Used to investigate structural separation between survival and non-survival outcomes.

---

## Validation Strategy

A **strict window temporal validation protocol** was adopted to prevent information leakage and to reflect realistic evaluation conditions:

- **Training:** 2007–2010  
- **Validation:** 2011  
- **Sliding Window:** 1
- 
Model performance was evaluated using **PR–ROC**, **Brier Score**, **Net Benefit**, with operating thresholds fixed from the validation set using **Youden’s J statistic** and applied unchanged to the held-out test set.

---

## Summary of Results

- **Best-performing model:**  
  Logistic Regression — PR–ROC = 0.842, Brier Score = 0.159, Mean Net Benefit = 0.367

- **Comparable performance:**  
  XGBoost — PR–ROC = 0.836, Brier Score = 0.159, Mean Net Benefit = 0.361
  Random Forest — PR–ROC = 0.842, Brier Score = 0.159, Mean Net Benefit = 0.366
  Gradient Boosting — PR–ROC = 0.831, Brier Score = 0.159, Mean Net Benefit = 0.365
  SVM — PR–ROC = 0.840, Brier Score = 0.159, Mean Net Benefit = 0.365

- **Baseline:**  
  Current Updated MELD — PR–ROC = 0.823, Brier Score = 0.204, Mean Net Benefit = 0.242

Overall, both PCA and UMAP indicate that post-transplant survival is not linearly separable, reinforcing the need for models capable of capturing complex nonlinear interactions among clinical variables.

---

## Ethics and Data Governance

This study was conducted using retrospective, anonymized registry data. All direct identifiers and potentially re-identifying variables were removed prior to data access, in accordance with the LGPD.

The study protocol was reviewed and approved by the appropriate Research Ethics Committee. Given the retrospective nature of the study and the exclusive use of anonymized data, the requirement for individual informed consent was waived.

---

## Data and Code Availability

The complete liver-transplant registry dataset cannot be publicly shared due to ethical, legal, and privacy constraints.

To promote scientific transparency and reproducibility, the data custodian has authorized the public release of a **carefully curated, fully anonymized reproducibility dataset**, limited to the minimum variables and records necessary to reproduce the analyses and results reported in the manuscript.

**In the event that the manuscript is accepted for publication**, the source code and the anonymized reproducibility dataset will be made publicly available in this repository.

---

## License

This project will be released under the **Apache License 2.0**.

---

## Acknowledgments

We would like to express our sincere gratitude and appreciation to **Francisco Monteiro, MD, PhD**, and to the **São Paulo State Department of Health (Secretaria de Estado da Saúde de São Paulo)** for providing access to the anonymized liver-transplant registry data used in this study.

---

## Citation

Please see **CITATION.cff** for the preferred citation of this repository and the associated manuscript.

---

## Disclaimer

This repository contains **research software only**.  
The models described herein are **not medical devices** and are **not intended for clinical decision-making** without appropriate regulatory approval and prospective clinical validation.

---

## Funding

This research was supported by the Institute for Technological Research (IPT) and the São Paulo Research Foundation (FAPESP).
