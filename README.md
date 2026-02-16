# Stacked Ensemble Models for Multi-Department Hospital Length of Stay (LOS) Prediction in Geriatric Patients

📌 **Conference Acceptance:**  
This research has been accepted for presentation at the **2026 International Society for Gerontechnology (ISG) World Conference**.

This repository contains my graduate research project focused on predicting **hospital Length of Stay (LOS)** for **geriatric patients** using the **MIMIC-IV** clinical database. The project combines **relational data engineering in PostgreSQL** with **Python-based machine learning**, with an emphasis on ensemble and stacked models across multiple hospital departments.

<p align="center">
  <img src="process flow.jpeg" width="750">
</p>


---

## Project Motivation

As aging populations place increasing pressure on hospital systems, accurate estimation of LOS is critical for:
- effective resource allocation,
- timely care coordination, and
- improved patient outcomes.

However, LOS prediction is challenging due to patient heterogeneity, comorbidities, and variability in departmental workflows. This project addresses these challenges by building **multi-department LOS models** and evaluating both **regression and classification** formulations using ensemble learning techniques.

---

## Project Overview

Key components of this work include:
- Ingesting and managing multi-table clinical data from MIMIC-IV
- Performing large-scale data cleaning, feature engineering, and aggregation
- Training LOS prediction models using:
  - **Regression** (continuous LOS)
  - **Classification** (LOS categories)
- Improving robustness and generalization through **ensemble and stacked models**
- Designing a reproducible and scalable data pipeline suitable for research and future extensions

---

## Data Architecture and Engineering

To improve clarity, reproducibility, and maintainability, the project uses a **two-layer PostgreSQL architecture**:

### RAW Database
- Stores MIMIC-IV tables **as-is**, with minimal preprocessing
- Preserves source fidelity and separates ingestion from transformation
- Serves as a stable foundation for downstream processing

### DATAMART Database
- Contains cleaned, transformed, and aggregated tables derived from RAW
- Implements cohort selection (geriatric population, department-level logic)
- Produces modeling-ready feature tables for Python workflows

This separation allows modeling experiments to evolve independently of data ingestion and ensures a cleaner research pipeline.

---

## Current Status

The core modeling framework—covering **regression, classification, and stacked ensemble approaches**—is largely complete.  
At this stage, I have intentionally taken a step back from final model execution to strengthen the **data storage and transformation layer**.

I am currently working on:
- Integrating PostgreSQL more systematically into the pipeline
- Finalizing the RAW → DATAMART transformations
- Ensuring clean, reproducible feature tables before final model training and evaluation

This step improves long-term scalability and aligns the project with best practices in data-driven research.

---

## Modeling Workflow

The modeling pipeline follows these steps:
1. Extract curated feature tables from the PostgreSQL DATAMART
2. Perform preprocessing and feature selection in Python
3. Train baseline regression and classification models
4. Evaluate department-specific LOS performance
5. Build and assess **stacked ensemble models**
6. Compare regression vs. classification results across departments

---

## Tools and Technologies

- **PostgreSQL** – relational storage and SQL transformations  
- **Python** – data processing and machine learning  
- **Jupyter Notebook / VS Code** – development and experimentation  
- **scikit-learn, pandas, numpy** – modeling and analysis  
- **GitHub** – version control and reproducibility  

---

## Data Access and Ethics

This project uses the **MIMIC-IV** dataset, which requires credentialed access and completion of required ethics training.  
No patient-level data is shared in this repository.

---

## Author

**Arpitha Thippeswamy**  
MSc Data Science – Graduate Research Project  
*Stacked Ensemble Models for Multi-Department Hospital Length of Stay Prediction in Geriatric Patients*

---

## Acknowledgements

- Johnson, A. E. W., et al. – **MIMIC-IV Clinical Database**
- Thompson Rivers University – Graduate Research Project
