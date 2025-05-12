# Evaluation of LLM Feature Importance Recognition and Prediction on Lung Disease

This project compares classical machine learning (CML) models and large language models (LLMs) for feature importance recognition and predictive performance on COVID-19 and other lung disease outcomes. We preprocess tabular clinical data, convert it into prompt-based datasets for LLMs, and evaluate both XGBoost/CatBoost and LLMs (ChatGPT-4o, Claude 3.7 Sonnet, DeepSeek Deepthink R1) across varied gender distributions. Our analysis highlights differences in feature prioritization, prediction bias, and overall accuracy, informing more equitable, hybrid modeling approaches.

## Final Report

- [Evaluation of LLM Feature Importance Recognition and Prediction on Lung Disease (PDF)](Evaluation%20of%20LLM%20Feature%20Importance%20Recognition%20and%20Prediction%20on%20Lung%20Disease.pdf)

## Repository Structure

```plaintext
Data/
├── Covid Data.csv                      # Original dataset from Mexican Federal Secretary of Health
├── Cleaned Covid Data.csv              # Data after preprocessing (missing values removed)
├── Cleaned Prompt Covid Data.csv       # Prompt-based dataset for LLM experiments
├── DataCleaning.ipynb                  # Script to process tabular data and generate prompt dataset
└── LLM_Test_Splits_By_Target/          # CSVs with prompts split by gender categories and targets:
     ├── AllMale_*                      # COVID Severity, Presence, Death, Pneumonia
     ├── AllFemale_*
     ├── AllFemalePregnant_*
     ├── GenderBalanced_*
     └── GenderUnbalanced_*

Feature Importance Comparisons/
└── Graphs/                              # Plots comparing feature importance across gender splits and model types

Feature Importance Output Files/
├── CML/                                 # Raw JSON outputs for XGBoost & CatBoost feature weights
└── LLM/                                 # Raw JSON outputs for LLM feature-importance predictions

Metric Output Files/
├── CML/                                 # Raw JSON metrics for CML models across splits & targets
└── LLM/                                 # Raw JSON metrics for LLM predictions across splits & targets

Notebooks & Scripts/
├── main_tabular.ipynb                   # Training/testing pipeline for XGBoost & CatBoost; collects metrics & feature weights
├── llm_tabular.ipynb                    # Prompt engineering & evaluation pipeline for LLMs; collects metrics & feature weights
└── LLM_vs_XGBoost_FeatureImportance_Comparison.ipynb  
                                         # Analysis notebook comparing LLM vs. CML feature importance
