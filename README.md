<div align="center">

  <h1><strong>Equity & Transportability of Plasma ATN Phenotypes</strong></h1>
  <h3><strong>Reproducible Analysis Pipeline for Evaluating Fairness, Calibration, and Population Transportability of Plasma Alzheimer’s Biomarkers</strong></h3>

  <p>
    <img src="https://img.shields.io/badge/Made%20with-R-276DC3.svg">
    <img src="https://img.shields.io/badge/Data-HRS%202016-blue.svg">
    <img src="https://img.shields.io/badge/Focus-Health%20Equity-purple.svg">
  </p>

</div>

---

# 🛠️ Repository Structure

| **Folder & File** | **Description** |
|-------------------|-----------------|
| **Code** | Full R Markdown pipeline (`Equity_Study.Rmd`) implementing all analyses (survey weighting, fairness metrics, calibration, interactions, sensitivity analyses) |
| **Figures** | All exported plots (fairness heatmaps, calibration curves, stratified associations, biomarker distributions) |
| **Tables** | CSV outputs for all tables (TPR/FPR by subgroup, calibration statistics, interaction models, stratified regressions, cutpoint analyses) |
| **Results** | Saved model objects, bootstrap outputs, and intermediate analysis artifacts |
| **Data** | *(Empty)* — HRS data must be obtained through the official portal; raw HRS data are not included |
| **License** | MIT License |

---

# 📘 Overview

This repository contains the complete reproducible analysis pipeline for the manuscript:

**Equity and Transportability of Plasma ATN Phenotypes in a Population‑Representative U.S. Aging Cohort**  
*Author: Emmanuel Fle Chea, MPH*

This project evaluates whether plasma Alzheimer’s biomarkers—amyloid (A), tau (T), and neurodegeneration (N)—perform equitably across demographic groups and whether biomarker‑cognition associations **transport** to the U.S. population when accounting for complex sampling.

Using **4,427 adults** from the **Health and Retirement Study (HRS) 2016 Venous Blood Study**, this pipeline quantifies:

- population‑representative ATN prevalence  
- weighted vs. unweighted biomarker‑cognition associations  
- fairness disparities across race, sex, and education  
- calibration failures in minoritized groups  
- race‑specific and education‑specific biomarker effects  
- sensitivity to cutpoints and missingness  
- implications for equitable biomarker‑based screening  

This repository is designed for **transparency**, **reproducibility**, and **open scientific practice**.

---

# 🧠 Scientific Background

## **ATN Framework**

| Component | Biomarker      | Interpretation        |
|----------|----------------|------------------------|
| **A**    | Aβ42/40 ratio  | Amyloid pathology      |
| **T**    | p‑tau181       | Tau pathology          |
| **N**    | NfL or GFAP    | Neurodegeneration / astrocytic injury |

ATN uses **binary cutpoints**, which may not generalize across diverse populations and may obscure continuous biological variation.

---

## **Equity & Transportability**

This project evaluates:

### **1. Transportability**
Do biomarker‑cognition associations derived from convenience samples hold in a nationally representative population?

### **2. Fairness**
Do biomarkers exhibit equal sensitivity, specificity, and calibration across:

- race  
- sex  
- education  
- intersectional groups (race × sex × education)  

### **3. Structural Disadvantage**
Does education (as a proxy for life‑course socioeconomic adversity) modify biomarker‑cognition relationships?

### **4. Calibration**
Do predicted risks match observed impairment rates across demographic groups?

---

# 📊 Key Findings (from the manuscript)

- Survey weighting **attenuates** amyloid and neurodegeneration associations by **45-50%**, revealing limited population‑level transportability.  
- Tau remains the **only robust** biomarker after weighting.  
- Biomarker sensitivity (TPR) is **>2× higher** in White vs. Black participants.  
- Black women show the **lowest sensitivity** across all education levels (TPR = 5-10%).  
- Calibration fails sharply in Black and Hispanic groups (slopes = 1.29–1.78).  
- Education modifies biomarker effects, producing **paradoxical positive amyloid associations** in low‑education groups.  
- Race‑specific Youden cutpoints differ by **30-40%**, indicating that universal thresholds may systematically misclassify minoritized individuals.  
- Equity gaps persist even after adjusting for vascular comorbidities.

---

# 🚀 Getting Started

### **1. Clone the Repository**
```bash
git clone https://github.com/efchea1/Equity-Transportability-Plasma-ATN-Phenotypes.git
cd Equity-Transportability-Plasma-ATN-Phenotypes

```
# 2. Install R and RStudio

* R ≥ 4.3.0

* RStudio (recommended)

# 3. Install Required R Packages

```{}
install.packages(c(
  # Core data manipulation & wrangling
  "dplyr", "tidyr", "tibble", "readr", "reshape2", "tidyverse",

  # Survey weighting & complex design
  "survey", "ResourceSelection",

  # Modeling & inference
  "nnet", "logistf", "lme4", "lmerTest", "PredictABEL", "rmda",

  # Fairness, clustering, and unsupervised methods
  "aricode", "cluster", "mclust", "fpc", "NbClust", "ppclust",

  # Dimensionality reduction
  "umap", "Rtsne", "factoextra",

  # Visualization
  "ggplot2", "ggpubr", "cowplot", "patchwork", "viridis",
  "corrplot", "pheatmap", "GGally", "ggdendro", "ggplotify",

  # Data quality & missingness
  "naniar",

  # Diagramming & network visualization
  "DiagrammeR", "DiagrammeRsvg", "networkD3", "htmlwidgets", "rsvg",

  # File handling & graphics
  "tiff", "magick", "webshot2", "gridExtra", "glue",

  # HRS data import
  "haven"
))
```

# 📁 Data Requirements
HRS data cannot be redistributed.

To reproduce the analysis:

Register at: https://hrs.isr.umich.edu

Request access to the 2016 Venous Blood Study biomarker files

Download the required datasets (SAS format)

Place them in your local working directory

Run the analysis pipeline (Equity_Study.Rmd), which includes all preprocessing and modeling steps

# 📜 Citation
If you use this code, please cite:

Chea, E.F.
**Equity and Transportability of Plasma ATN Phenotypes in a Population‑Representative U.S. Aging Cohort.**  
Preprint DOI: In progress

Peer‑review journal submission: In preparation for **eLife**

# 👤 Author
Emmanuel Fle Chea, MPH  
Independent Researcher • Health Data Scientist • Equity‑Focused Methodologist
📧 **Email:** emmanuelf.chea@gmail.com

# 📄 License
This project is released under the MIT License.
See the LICENSE file for full terms.
You are free to reuse, modify, and build upon this work with attribution.
