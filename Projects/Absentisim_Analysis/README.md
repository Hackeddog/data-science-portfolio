# Absenteeism Analysis — Full-Stack Predictive Analytics Project

This project is an end-to-end data science workflow for analyzing and predicting employee absenteeism. It connects **Python**, **machine learning**, **SQL**, and **Tableau** into one analytics pipeline: raw HR absenteeism records are cleaned and transformed in Python, passed through a trained machine learning model, exported as prediction outputs, structured for SQL storage, and visualized in Tableau for business analysis.

## Project Goal

The goal is to identify employees or absence records that are more likely to result in excessive absenteeism. Instead of only describing historical absences, this project adds a predictive layer by estimating the probability that a future absence record belongs to a high-absenteeism category.

This supports questions such as:

- Which absence reasons are most associated with higher absenteeism risk?
- Which employee attributes appear in higher-risk records?
- How can prediction probabilities be stored and analyzed in a database?
- How can model outputs be turned into a dashboard for decision-making?

## Full-Stack Analytics Workflow

```text
Raw CSV Data
   ↓
Python Data Cleaning & Feature Engineering
   ↓
Machine Learning Model + Scaler
   ↓
Prediction Output CSV
   ↓
SQL Table for Predicted Outputs
   ↓
Tableau Dashboard / Visual Analysis
```

## Tools and Technologies

| Layer | Tools Used | Purpose |
|---|---|---|
| Data Processing | Python, Pandas, NumPy | Load, clean, transform, and prepare absenteeism records |
| Machine Learning | scikit-learn, pickle | Scale features and generate prediction probabilities/classes |
| Data Storage | SQL | Define a structured table for predicted outputs |
| Visualization | Tableau | Build visual analysis from prediction-ready data |
| File Outputs | CSV | Store raw, preprocessed, new, and predicted datasets |

## Repository Files

| File | Description |
|---|---|
| `raw_data.csv` | Original absenteeism dataset with 700 rows and 12 columns |
| `df_preprocessed.csv` | Cleaned and feature-engineered dataset used for modeling/analysis |
| `Absenteeism_new_data.csv` | New unseen records prepared for prediction |
| `Absenteeism_prediction.csv` | Final model output containing prediction probabilities and predicted classes |
| `absenteeism_module` | Python module that loads the model/scaler, preprocesses new data, and generates predictions |
| `model` | Serialized trained machine learning model saved with pickle |
| `scaler` | Serialized custom scaler used to transform numerical features consistently |
| `sql_query.sql` | SQL script that creates the database/table for predicted outputs |
| `analysis_tableau.twb` | Tableau workbook for visual analysis of absenteeism predictions |

## Dataset Overview

The raw dataset contains employee absenteeism records with fields related to absence reason, date, commute, workload, demographics, family factors, and total absenteeism time.

### Raw Data Fields

| Field | Meaning |
|---|---|
| `ID` | Employee identifier |
| `Reason for Absence` | Numeric category describing the reason for absence |
| `Date` | Date of absence record |
| `Transportation Expense` | Employee transportation cost |
| `Distance to Work` | Distance between home and work |
| `Age` | Employee age |
| `Daily Work Load Average` | Average workload value for the day/period |
| `Body Mass Index` | Employee BMI |
| `Education` | Education category |
| `Children` | Number of children |
| `Pets` | Number of pets |
| `Absenteeism Time in Hours` | Number of absence hours |

## Python Preprocessing and Feature Engineering

The Python module performs the same transformation logic needed to make new records compatible with the trained model.

Key preprocessing steps include:

1. **Load new absenteeism records** from `Absenteeism_new_data.csv`.
2. **Drop the employee ID** because it is an identifier, not a predictive feature.
3. **Transform absence reason codes** into four grouped dummy variables:
   - `Reason_1`
   - `Reason_2`
   - `Reason_3`
   - `Reason_4`
4. **Convert the date column** into a datetime format.
5. **Extract month value** from the date for seasonality/time-based analysis.
6. **Create day-of-week feature**, then remove it later based on model feature selection.
7. **Map education categories** into a binary variable:
   - `0` for basic education
   - `1` for higher education categories
8. **Remove columns not used by the final model**, including:
   - `Day of the Week`
   - `Daily Work Load Average`
   - `Distance to Work`
9. **Apply the saved scaler** to numerical features using the custom scaler class.
10. **Generate model outputs**:
   - `Probability`
   - `Prediction`

## Machine Learning Component

The project uses a saved machine learning model and scaler to predict absenteeism risk for new data.

The `absenteeism_module` contains two main classes:

### `CustomScaler`

A custom scikit-learn compatible transformer that scales only selected numerical columns while preserving the original column order. This is important because machine learning models expect features to appear in the same order and scale as during training.

### `absenteeism_model`

A reusable model wrapper that:

- Loads the saved model file
- Loads the saved scaler file
- Cleans and transforms new data
- Produces prediction probabilities
- Produces binary prediction categories
- Returns a final prediction-ready dataframe

### Prediction Output

`Absenteeism_prediction.csv` contains 40 prediction records with these columns:

| Field | Meaning |
|---|---|
| `reason_1` to `reason_4` | Grouped absence reason indicators |
| `month_value` | Month extracted from the absence date |
| `transportation_expense` | Transportation cost feature |
| `age` | Employee age |
| `body_mass_index` | BMI feature |
| `education` | Binary education indicator |
| `children` | Number of children |
| `pets` | Number of pets |
| `probability` | Model-estimated probability of high absenteeism |
| `prediction` | Final predicted class: `0` or `1` |

## SQL Integration

The SQL script creates a database and table for storing model predictions.

```sql
create database predicted_outputs;
use predicted_outputs;

drop table if exists predicted_outputs;
create table predicted_outputs
(
    reason_1 bit not null,
    reason_2 bit not null,
    reason_3 bit not null,
    reason_4 bit not null,
    month_value int not null,
    transportation_expense int not null,
    age int not null,
    body_mass_index int not null,
    education bit not null,
    children int not null,
    pets int not null,
    probability float not null,
    prediction bit not null
);
```

This database layer makes the project more than a notebook analysis. It prepares the prediction results for downstream querying, reporting, dashboarding, or integration into business intelligence tools.

## Tableau Visualization

The Tableau workbook, `analysis_tableau.twb`, is used to turn prediction outputs into visual insights. The dashboard can be used to analyze patterns such as:

- Distribution of predicted absenteeism risk
- High-probability absence records
- Risk by reason category
- Risk by month
- Employee attribute patterns such as age, BMI, children, pets, and transportation expense

Tableau adds the business intelligence layer by making model results easier to explore and communicate.

## How to Use This Project

### 1. Review the Data

Start with:

- `raw_data.csv` for the original dataset
- `df_preprocessed.csv` for the cleaned version
- `Absenteeism_new_data.csv` for new records to predict

### 2. Run the Prediction Module

The module is designed to load the saved `model` and `scaler`, preprocess new data, and generate predictions.

Example usage:

```python
from absenteeism_module import absenteeism_model

model = absenteeism_model('model', 'scaler')
model.load_and_clean_data('Absenteeism_new_data.csv')
predictions = model.predicted_outputs()
print(predictions.head())
```

### 3. Store Outputs in SQL

Use `sql_query.sql` to create the database table, then load `Absenteeism_prediction.csv` into the `predicted_outputs` table.

### 4. Explore in Tableau

Open `analysis_tableau.twb` and connect it to the prediction output data to explore the dashboard and insights.

## Business Value

This project demonstrates how predictive analytics can support workforce and operations planning. By estimating absenteeism risk, organizations can:

- Identify potential high-absence cases earlier
- Understand the relationship between absence reasons and absence risk
- Monitor absenteeism trends over time
- Support HR planning and resource allocation
- Turn machine learning outputs into dashboard-ready business insights

## Skills Demonstrated

- Data cleaning and preprocessing with Python
- Feature engineering for machine learning
- Custom scikit-learn transformer design
- Model serialization and reuse with pickle
- Predictive probability scoring
- SQL schema design for analytics outputs
- Tableau dashboarding and visual storytelling
- End-to-end data workflow thinking

## Limitations and Future Improvements

Possible improvements include:

- Add a training notebook showing model selection, evaluation, and metrics
- Include model performance scores such as accuracy, precision, recall, F1-score, and ROC-AUC
- Automate loading prediction outputs into SQL
- Add a Tableau dashboard screenshot to this README
- Include more advanced feature importance analysis
- Deploy the prediction workflow as an API or scheduled pipeline

## Conclusion

The Absenteeism Analysis project shows a full-stack data science workflow from raw data to predictive insight. It combines Python preprocessing, machine learning, SQL storage, and Tableau visualization to demonstrate how analytical systems can move beyond static reporting and support data-driven decision-making.
