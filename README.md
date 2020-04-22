## COVID-19 Prediction Model
From the paper: 

Noam Barda et al., **Performing risk stratification for COVID-19 when individual level data is not available – the experience of a large healthcare organization.**


## Model Predictors and Exact Variable Names
* **Age** - age_in_days
* **Sex** - sex
* **Pack years** - pack_years
* **COPD** - COPD_by_chr
* **Number of wheezing / dyspnea diagnoses** - diag_wheezing_dyspnea_count
* **Albumin** - labs_albumin_last_value
* **Red cell distribution width** - labs_rdw_last_value
* **C-Reactive Protein** - labs_cpr_last_value
* **Urea** - labs_urea_blood_last_value
* **Lymphocyte%** - labs_lym_percent_last_value
* **Chlroide** - labs_chloride_last_value
* **Creatinine** - labs_createnine_blood_last_val
* **High Density Lipoprotein** - labs_cholesterol_hdl_last_valu
* **Duration of hospitalizations** - hosps_total_duration
* **Count of hospitalizations** - hosps_total_count
* **Count of ambulance rides** - ambulances_between_hospitals_c
* **Count of Sulfonamide dispenses** - meds_sulfonamides_count
* **Count of Anti-cholinergic dispenses** - meds_anticholinergics_count
* **Count of Glucocorticoid dispenses** - meds_glucocorticoids_count
* **Chronic Respiratory Disease** - Chronic_Respiratory_Disease
* **Cardiovascular Disease** - CVD
* **Diabetes** - Diabetes
* **Malignancy** - Cancer
* **Hypertension** - Hypertension

## Model Outcome
The probability of death due to a COVID-19 infection, having been infected with the virus.


## Multicalibration Correction Table
To adjust the predictors to the COVID-19 outcome.

| Age Group     | Male         | Female     |
| ------------- |:------------:| ----------:|
| 10-19         | +0.003       | -0.011214  |
| 20-29         | +0.00368     | -0.010539  |
| 30-39         | +0.00086     | -0.013356  |
| 40-49         | +0.00723     | -0.006987  |
| 50-59         | +0.01217     | -0.002049  |
| 60-69         | +0.02944     | +0.01523   |
| 70-79         | +0.05912     | +0.0449    |
| 80+           | +0.08484     | +0.07063   |

## Use
1. Import the predictor (COVID_19_model.txt) using LightGBM 2.2.3 on Python.

2. Predict using your data.

3. Correct the predictions according to each row's age and sex, by adding the appropriate  values from the correction table.# COVID-19-Model
