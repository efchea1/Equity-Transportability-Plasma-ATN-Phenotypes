<div align="center">

<h1><strong>Equity & Transportability of Plasma ATN Phenotypes</strong></h1>
<h3><strong>Reproducible Pipeline for Fairness, Calibration, and Population‑Representative Evaluation of Plasma Alzheimer’s Biomarkers</strong></h3>

<p>
<img src="https://img.shields.io/badge/Made%20with-R-276DC3.svg">
<img src="https://img.shields.io/badge/Data-HRS%202016-blue.svg">
<img src="https://img.shields.io/badge/Focus-Health%20Equity-purple.svg">
<img src="https://img.shields.io/badge/Open%20Science-Reproducible-green.svg">
</p>

</div>

---

# 📘 Overview
This repository contains the complete, fully reproducible analysis pipeline for the manuscript:

**Equity and Transportability of Plasma ATN Phenotypes in a Population‑Representative U.S. Aging Cohort** 
**Author:** Emmanuel Fle Chea, MPH

Using 4,427 adults from the Health and Retirement Study (HRS) 2016 Venous Blood Study, this project evaluates whether plasma Alzheimer’s biomarkers—amyloid (A), tau (T), and neurodegeneration (N)—perform equitably across demographic groups and whether biomarker–cognition associations transport to the U.S. population when accounting for complex sampling.

The pipeline quantifies:

- population‑representative ATN prevalence

- weighted vs. unweighted biomarker–cognition associations

- fairness disparities across race, sex, and intersectional groups

- calibration failures in minoritized populations

- education as structural disadvantage

- race‑specific and education‑specific biomarker effects

- sensitivity to cutpoints and missingness

- implications for equitable biomarker‑based screening

This repository is designed for transparency, reproducibility, and open scientific practice, consistent with FAIR principles.

---

# 🧠 Scientific Background

## **ATN Framework**

| Component | Biomarker      | Interpretation        |
|----------|----------------|------------------------|
| **A**    | Aβ42/40 ratio  | Amyloid pathology      |
| **T**    | p‑tau181       | Tau pathology          |
| **N**    | NfL or GFAP    | Neurodegeneration / astrocytic injury |

ATN cutpoints are typically derived from highly selected clinical cohorts. This project evaluates whether these thresholds and associations **generalize** to a nationally representative population.

---

# Equity, Fairness & Transportability

This study addresses four core questions:

1. Transportability

Do biomarker–cognition associations derived from convenience samples hold in a probability‑sampled U.S. population?

2. Fairness

Do biomarkers exhibit equal sensitivity, specificity, and calibration across:

- race

- sex

- education

- intersectional groups (race × sex × education)

3. Structural Disadvantage

Does education, used here as a proxy for life‑course socioeconomic adversity, modify biomarker–cognition relationships?

4. Calibration

Do predicted risks match observed impairment rates across demographic groups?

---

# 🛠️ Repository Structure

| **Folder & File** | **Description** |
|-------------------|-----------------|
| **Code** | Full R Markdown pipeline (`Equity_Study.Rmd`) implementing all analyses: survey weighting, fairness metrics, calibration, interactions, sensitivity analyses |
| **Figures** | All exported plots (fairness heatmaps, calibration curves, stratified associations, biomarker distributions, etc.) |
| **Tables** | CSV outputs for all tables (TPR/FPR by subgroup, calibration statistics, interaction models, stratified regressions, cutpoint analyses, etc.) |
| **Results** | Saved model objects, bootstrap outputs, and intermediate analysis artifacts |
| **Data** | *(Empty)* — (Empty) — HRS data cannot be redistributed; users must obtain data from HRS |
| **License** | MIT License |

---

# 🚀 Getting Started

### **1. Clone the Repository**
```bash
git clone https://github.com/efchea1/Equity-Transportability-Plasma-ATN-Phenotypes.git
cd Equity-Transportability-Plasma-ATN-Phenotypes
```

---

# Install R and RStudio

- R ≥ 4.3.0

- RStudio recommended

---

# 3. Install Required R Packages

```
packages <- c(
  "dplyr","tidyr","ggplot2","survey","pROC","tableone","knitr","kableExtra",
  "gridExtra","scales","broom","boot","caret","haven","DiagrammeR",
  "DiagrammeRsvg","rsvg","cutpointr","readr","plotROC","ROCR"
)

install.packages(setdiff(packages, rownames(installed.packages())))
```

---

# 📁 Data Requirements

To reproduce the analysis:

1. Register at: https://hrs.isr.umich.edu

2. Request access to the 2016 Venous Blood Study biomarker files

3. Download the required SAS datasets

4. Place them in your working directory

5. Run `Equity_Study.Rmd`

The pipeline includes all preprocessing, survey design specification, modeling, and figure/table generation.

---

# 📜 Citation

If you use this code, please cite:

**Chea, E.F.**
*Equity and Transportability of Plasma ATN Phenotypes in a Population‑Representative U.S. Aging Cohort.*  

Preprint DOI: In progress

Submitted to **eLife**

---

# 👤 Author
**Emmanuel Fle Chea, MPH**  
Independent Researcher • Health Data Scientist • Equity‑Focused Methodologist
📧 **Email:** emmanuelf.chea@gmail.com

---

# 📄 License
This project is released under the **MIT License**.
You are free to reuse, modify, and build upon this work with attribution.
