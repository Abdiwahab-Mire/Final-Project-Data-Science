SMART Survey Processing Pipeline & ML-Based Mortality Prediction
Data Science Final Year Project

Faculty of Computing and Informatics, SIMAD University

Course / Instructor: Data Science | Dr. Yahye Abukar

📌 Project Overview
This repository contains an end-to-end data processing pipeline and machine learning framework designed to extract, clean, aggregate, and analyze raw SMART survey files (.as files).

The primary objective is to transform non-standard survey files into an analysis-ready dataset and deploy supervised machine learning models to predict mortality outcomes.

🛠 Project Architecture & Pipeline Stages
The repository structured around a 4-stage processing pipeline followed by predictive modeling:

Raw .as Files ➔ Stage 1: Classify & Structure ➔ Stage 2: Extract to CSV ➔ Stage 3: Clean & Compute Person-Time ➔ Stage 4: Merge & Export ➔ Machine Learning Models
Stage 1: Organize and Classify Surveys
Parses raw .as survey files to extract spatial metadata (location, admin level) and temporal metadata (survey dates).

Identifies survey structural types (Individual vs. Aggregate, Admin2 vs. LHZ).

Standardizes file naming conventions and organizes them into a clean directory tree.

Stage 2: Convert to CSV
Extracts individual and aggregate mortality sections from parsed survey files.

Converts custom structures into clean, tabular standard CSV outputs.

Stage 3: Clean & Compute Household Information
Aggregates person-level observations into household-level summaries (one row per household).

Computes household counts and Person-Time metrics required for accurate epidemiological mortality rate calculations.

Stage 4: Final Analysis Dataset Integration
Harmonizes district names, geospatial labels, and date formats across all records.

Merges disparate survey tables into a single, unified, analysis-ready master CSV dataset.

🤖 Machine Learning & Evaluation
Selected supervised learning algorithms are trained on the unified dataset to predict mortality outcomes:

Logistic Regression: Baseline probabilistic linear classifier.

Random Forest: Ensemble decision-tree approach to minimize overfitting and evaluate feature importance.

XGBoost: Gradient-boosted decision trees focused on maximizing classification metrics on imbalanced data.

Evaluation Metrics
Model performance is evaluated and compared using:

Accuracy

Recall (Prioritized metric due to the critical nature of minimizing false negatives in mortality prediction)

F1-Score / F-Measure

Area Under the ROC Curve (AUC)

Confusion Matrices

📂 Repository Structure
Plaintext
├── data/
│   ├── raw/                  # Initial raw .as survey files
│   ├── processed/            # Intermediate extracted CSVs
│   └── final/                # Cleaned, merged master dataset
├── notebooks/                # Jupyter Notebooks for EDA and testing
├── src/                      # Source code modules
│   ├── ml_pipline .py             y    # Classification and renaming script
│   ├── organize_surveys.py     # CSV extraction script
│   ├── process_households  # Household aggregation & person-time script
│   ├── merge_surveys.py       # Final dataset preparation script
│   └── train_models.py       # ML training and evaluation script
        selected_model.py
├── outputs/                  # Saved models, confusion matrix figures, and evaluation tables
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation
⚙️ Setup and Installation
Prerequisites
Python 3.8+

pip package manager

Installation Steps
Clone the repository:

Bash
git clone https://github.com/your-username/smart-survey-mortality-prediction.git
cd smart-survey-mortality-prediction
Create and activate a virtual environment (optional but recommended):

Bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install dependencies:

Bash
pip install -r requirements.txt
🚀 Execution Guide
Run the pipeline sequentially using the scripts in src/:

Bash
# Stage 1: Classify and organize survey files
ml_pipline.py

# Stage 2: Extract survey sections to CSV
organize_survery.py

# Stage 3: Compute household metrics & person-time
process_households.py

# Stage 4: Merge final dataset
merge_surveys.py

# Train models and generate evaluation metrics
python src/train_models.py
📄 Documentation & Report Format
The final report documenting the methodology, mathematical rationale behind Person-Time calculation, detailed algorithm performance comparisons, and APA 7th Edition citations is available in PDF format upon request or in the project submission package.
