# Churn Prediction Case Study: Mobile Money Analytics

This repository presents a data science case study focused on investigating,diagnosing and improving a churn prediction model for a leading mobile money platform. It includes exploratory data analysis (EDA), rebuilding the model and validating it's performance.

## Project Structure

```
├── data/
│   └── 01-raw/              # Raw CSV data files
├── notebooks/               # Jupyter notebooks
├── images/                  # Visualizations
├── CASE_STUDY_BRIEF.md      # Problem statement
├── model_documentation.txt  # Model logic & performance
└── requirements.txt         # Dependencies
```

## Getting Started

### 1. Clone Repository

```bash
git clone https://github.com/Kobeyvines/CASE_STUDY.git
cd CASE_STUDY
```

### 2. Set Up Virtual Environment

```bash
# Create the environment
conda create --name case_study_env python=3.10 -y

# Activate the environment
conda activate case_study_env
```

### 3. Install Dependencies

```bash
# Install pip inside your conda env if not present
conda install pip -y

# Install the required packages
pip install -r requirements.txt
```

If `requirements.txt` is missing, install:

```
pandas numpy matplotlib seaborn scikit-learn
```

### 4. Data

Raw data is located in:

```
data/01-raw/
```

## Workflow
*   **Exploratory Data Analysis (EDA):** Located in the notebooks/ folder. This covers, investigations, data distributions, missing value analysis, and feature correlations.
    
*   **Diagnosis:** An audit of the legacy model's performance. Our investigation found that the reported 87% accuracy claim was incorrect, necessitating a complete model overhaul.
    
*   **Model Rebuilding:** Implementation of a new classification pipeline designed for transparency and verifiable metrics.
    
*   **Evaluation:** Models were evaluated using a comprehensive **Classification Report**, providing insights into Precision, Recall, and F1-scores to ensure a balanced view of model effectiveness beyond simple accuracy.

## Key Insights

- Original model accuracy was off in real word setting (deployment env). 
- Rebuilt model balances precision and recall for retention campaigns.

## Tech Stack

- **Language:** Python  
- **Libraries:** Pandas, Scikit-Learn, Matplotlib, Seaborn  
- **Environment:** Jupyter Notebooks  

**Author:** Kobeyvines  
**Status:** Completed - February 2026