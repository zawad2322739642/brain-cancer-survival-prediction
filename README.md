# Brain Cancer Survival Prediction (Decision Tree vs. XGBoost)

This repository contains a machine learning workflow comparing **Decision Tree** and **XGBoost** classifiers to predict patient survival status (`status`) using clinical brain cancer data (`DT-BrainCancer.csv`).

## Project Overview
* **Dataset:** 88 clinical records with features including `sex`, `diagnosis` (Meningioma, HG glioma, LG glioma, Other), tumor location (`loc`), Karnofsky Performance Status (`ki`), and Gross Tumor Volume (`gtv`).
* **Data Split:** 70% Training (62 rows), 15% Validation (13 rows), 15% Testing (13 rows).
* **Custom Evaluation:** Precision, Recall, F1-score, Confusion Matrix, and Precision-Recall (PR) curves implemented from scratch using NumPy.
* **Optimization:** Grid search hyperparameter tuning performed on the validation set optimizing for Class 1 F1-score.

## Key Results (Test Set)
| Model | Accuracy | Precision | Recall | F1-Score | Average Precision (AP) |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Baseline (Majority Class)** | 76.9% | 0.00 | 0.00 | 0.00 | - |
| **Decision Tree** | 84.6% | 0.60 | 1.00 | 0.75 | 0.533 |
| **XGBoost** | 84.6% | 0.60 | 1.00 | 0.75 | **0.917** |

## Repository Structure
* `notebook.ipynb` — Main Jupyter/Colab notebook containing EDA, preprocessing, tuning, and evaluation.
* `DT-BrainCancer.csv` — Dataset used for training and evaluation *(upload this alongside your notebook)*.
* `results/` — Exported CSV tables of hyperparameter grid search results.
* `figures/` — Generated 300-DPI plots (PR curves, confusion matrices, feature importance, and decision tree visualization).

## Requirements
```bash
pip install numpy pandas matplotlib scikit-learn xgboost
