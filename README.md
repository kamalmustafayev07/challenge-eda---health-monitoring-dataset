# Healthcare Patient Monitoring Dataset - Challenge C

## Overview
This project addresses **Challenge C**, involving the cleaning, exploratory data analysis (EDA), and preparation of a synthetic healthcare patient monitoring dataset for future predictive modeling.

The dataset contains daily health and lifestyle metrics for 300 patients, including:
- Heart rate
- Glucose level
- Steps
- Calories burned
- Sleep hours
- BMI
- Smoking status (categorical: non-smoker, former, current)
- Alcohol intake
- Exercise hours
- Stress level

## Objectives Completed
- Cleaned missing values and handled unrealistic measurements.
- Visualized distributions and relationships of key health indicators.
- Investigated correlations between lifestyle factors and health metrics.
- Developed data-driven hypotheses for future predictive modeling.
- Produced a cleaned, normalized dataset ready for machine learning.

## Dataset
- **Original**: `health_monitoring_synthetic.csv` (300 rows × 10 columns)
- **Cleaned Output**: `health_monitoring_cleaned.csv`

### Key Cleaning Steps
1. Identified missing values:
   - `sleep_hours`: 10 missing
   - `BMI`: 10 missing
   - Other columns: complete
2. Filled missing values using mean imputation (preserving overall distribution).
3. Checked for unrealistic outliers via boxplots (no extreme anomalies requiring removal).
4. Normalized all numeric columns except `smoking_status` (using z-score standardization) for consistent scaling in modeling.
5. Encoded `smoking_status` numerically (0=non-smoker, 1=former, 2=current) for correlation analysis.

## Exploratory Data Analysis
### Visualizations (in notebook)
- Individual boxplots for health metrics to detect outliers.
- Correlation heatmap showing relationships between all variables.

### Key Correlation Insights
| Relationship                          | Correlation | Interpretation                                      |
|---------------------------------------|-------------|-----------------------------------------------------|
| Steps ↔ Calories                      | Strong +    | Higher activity strongly linked to calorie burn     |
| Glucose Level ↔ BMI                   | Positive    | Elevated glucose associated with higher BMI         |
| Stress Level ↔ Sleep Hours            | Strong -    | Higher stress linked to reduced sleep               |
| Exercise Hours ↔ Heart Rate           | Negative    | More exercise associated with lower resting HR      |
| Smoking Status ↔ Heart Rate           | Positive    | Smoking correlates with higher heart rate           |
| Alcohol Intake ↔ Stress Level         | Positive    | Higher alcohol linked to higher reported stress     |

## Hypotheses for Predictive Modeling
| Hypothesis                                                          | Target Variable       | Key Predictors                              |
|---------------------------------------------------------------------|-----------------------|---------------------------------------------|
| Physical activity reduces excess calorie intake                     | Calories              | Steps                                       |
| BMI can be predicted from metabolic and lifestyle factors          | BMI                   | Glucose level, smoking, alcohol             |
| Stress level influenced by sleep, exercise, and alcohol             | Stress Level          | Sleep hours, exercise hours, alcohol intake |
| Resting heart rate impacted by fitness and smoking habits           | Heart Rate            | Exercise hours, smoking status              |

These hypotheses support future regression or classification tasks (e.g., risk prediction, health outcome forecasting).

## Files
- `health_care_cleaning.ipynb`: Complete Jupyter notebook with cleaning, visualizations, analysis, and insights.
- `health_monitoring_synthetic.csv`: Original raw dataset.
- `health_monitoring_cleaned.csv`: Final cleaned and normalized dataset (ready for modeling).

## Usage
1. Open the notebook to review the full analysis and visualizations.
2. Use `health_monitoring_cleaned.csv` as input for machine learning models (e.g., regression, clustering, risk scoring).

## Tools & Libraries
- Python 3
- pandas, numpy
- matplotlib, seaborn (for plots)

This project provides a solid foundation for building predictive healthcare analytics models.

