# Newborn Hospitalization Costs in New York City

A machine learning and healthcare analytics project focused on identifying the main drivers of newborn hospitalization costs across New York City hospitals using 2024 SPARCS inpatient discharge data.

## Project Overview

This project examines how clinical, demographic, and healthcare system factors contribute to variation in newborn hospitalization costs in New York City. The goal is to support hospital leadership, especially financial decision-makers, in understanding cost patterns, improving forecasting, and identifying areas for operational review.

The analysis was designed around four main questions:

- What are the main drivers of newborn hospitalization costs in New York City?
- How much do costs vary across hospitals, patient groups, and clinical conditions?
- Which variables are most important for explaining cost differences?
- Which regression or machine learning model performs best in predicting total newborn hospitalization cost?

## Dataset

The project uses the **2024 SPARCS hospital discharge dataset** filtered to **newborn inpatient cases in New York City facilities**. The data includes clinical, demographic, and hospital system variables relevant to newborn hospitalization outcomes and cost. 

Dataset can be found [HERE](https://health.data.ny.gov/Health/Hospital-Inpatient-Discharges-SPARCS-De-Identified/sf4k-39ay/data_preview).


### Example variables used
- Length of Stay
- APR Severity of Illness
- APR DRG Code
- Birth Weight
- Race / Ethnicity
- Zip Code
- Payment Typology
- Facility Name
- Emergency Department indicator
- Total Charges
- Total Costs

## Project Goals

The purpose of this project is to identify which factors most strongly influence newborn hospitalization costs and to build predictive models that can estimate total cost accurately. The broader motivation is to help hospital systems move toward more proactive and risk-adjusted financial planning. :contentReference[oaicite:2]{index=2}

## Methodology

The workflow for this project included:

1. **Data preprocessing**
   - Filtering newborn cases
   - Handling missing values
   - Encoding categorical variables
   - Scaling numerical features when needed

2. **Feature engineering**
   - Creating and analyzing the **Cost-to-Charge Ratio (CCR)** to better understand differences between actual cost and billed charges across facilities. :contentReference[oaicite:3]{index=3}

3. **Exploratory data analysis**
   - Examining cost variation across severity levels, hospitals, payer groups, race/ethnicity, and gender
   - Comparing average costs and cost distributions across major categories

4. **Model benchmarking**
   - Multiple models were compared, including traditional linear approaches and more advanced machine learning methods
   - Linear Regression, Lasso, Ridge, Support Vector Machines, Multilayer Perceptrons, Random Forest, and XGBoost were part of the broader benchmarking process. :contentReference[oaicite:4]{index=4}

5. **Model selection**
   - Random Forest was selected as the final model because it delivered the strongest predictive performance and handled nonlinear relationships well. :contentReference[oaicite:5]{index=5}

## Key Findings

### 1. Clinical severity and length of stay are the biggest cost drivers
Clinical and operational variables overwhelmingly explain newborn hospitalization cost variation. In particular, **Length of Stay (LOS)** was identified as the single strongest predictor of cost, with overall clinical and operational features accounting for the vast majority of model influence. :contentReference[oaicite:6]{index=6}

### 2. Payment typology matters less than expected
Payment typology had relatively low predictive importance in the model, although descriptive analysis still showed notable variation across payer categories. Some groups such as “Miscellaneous/Other” and “Managed Care, Unspecified” appeared to have unusual cost patterns worth further monitoring. :contentReference[oaicite:7]{index=7}

### 3. Facility-level variation is substantial
Average newborn costs varied widely across NYC hospitals. For example, NewYork-Presbyterian Hospital (Columbia Presbyterian Center) and NYU Langone showed much higher average costs than some other facilities, suggesting both case complexity and facility-level pricing differences may be contributing. :contentReference[oaicite:8]{index=8}

### 4. Demographic disparities were visible in descriptive analysis
Although demographic factors contributed relatively little to predictive power, descriptive analysis showed meaningful differences in costs and CCR across racial groups. Black/African American newborns had higher average costs and higher CCR values than White newborns, suggesting broader structural or upstream care inequities may be influencing outcomes. :contentReference[oaicite:9]{index=9}

## Model Performance

The final **Random Forest** model achieved strong predictive performance:

- **R²:** 0.9937
- **MAE:** \$606.24
- **RMSE:** \$4,784.88

Compared with the baseline linear model, the Random Forest substantially reduced prediction error and provided a much better fit for the nonlinear structure of the data. :contentReference[oaicite:10]{index=10}

## Tools and Technologies

- Python
- Jupyter Notebook
- pandas
- numpy
- scikit-learn
- matplotlib / seaborn
- SPARCS healthcare data
