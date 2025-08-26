# EEG Alpha Power and Connectivity Analysis
EEG-based ML pipeline for classifying eyes-open vs. eyes-closed states, extracting PSD features, and analyzing alpha band power in relation to age. Includes preprocessing, SVM/Random Forest/Logistic Regression models, hyperparameter tuning, and McNemar’s test evaluation. This repository contains the analysis and modeling pipeline for investigating EEG alpha power, functional connectivity, and their relationship with age and sex. The project explores both descriptive statistics and predictive modeling to characterize developmental and aging-related patterns in EEG.

## Project Overview
The project is structured around three main research questions:

1. Can eyes-open (EO) and eyes-closed (EC) EEG data be distinguished using machine learning models?  
2. How does alpha power (absolute and relative) change across the lifespan, and are there sex-related differences?  
3. How does EEG coherence (standard and imaginary) vary with age, and what can it reveal about functional brain connectivity?  

Methods include spectral analysis using **Welch’s method**, classification with **Logistic Regression, Support Vector Machines, and Random Forests**, as well as **ensemble modeling**. Statistical evaluation is performed using **McNemar’s test** and **two-way ANOVA**.

## Repository Structure

### Data Analysis and Feature Extraction
- **`calculate_alpha_power.ipynb`** – Computes alpha power using Welch’s method across all channels.  
- **`mean_alpha_power.ipynb`** – Aggregates absolute and relative alpha power across subjects, grouped by age and sex.  
- **`random_chosen_epochs_EO_age_.ipynb`** – Compares age-related alpha power trajectories using random vs. EO-only epochs.

### Connectivity Analysis
- **`coherence.ipynb`** – Estimates standard and imaginary coherence in the alpha band, analyzing developmental and aging trajectories.  

### Classification Models
- **`MLR.ipynb`** – Multinomial Logistic Regression model for age-group classification.  
- **`RFC.ipynb`** – Random Forest Classifier for non-linear age-group classification.  
- **`LR_SVM_RF_ensemble_predictions_.ipynb`** – Trains Logistic Regression, SVM, and RF, then combines them via a soft-voting ensemble.  

### Statistical Evaluation
- **`McNemars_rq1.ipynb`** – Applies McNemar’s test to compare classifiers for EO vs. EC discrimination.  
- **`McNemars_rq2.ipynb`** – Applies McNemar’s test to age-group classification results.  
- **`ANOVA.ipynb`** – Two-way ANOVA testing effects of model type (MLR vs. RF) and data type (EC, EO, Random) on classification accuracy.

## Results Summary
- RF models consistently outperformed MLR, showing robust age-related patterns across EEG conditions.
- Alpha power increased during childhood, stabilized in adulthood, and declined in older age, with small but consistent sex effects.
- Coherence analyses revealed developmental peaks in connectivity and gradual declines with age, particularly in imaginary coherence.

## Requirements

- Python 3.9+  
- [MNE](https://mne.tools/stable/index.html)  
- NumPy, SciPy, Pandas  
- scikit-learn  
- Matplotlib, Seaborn
