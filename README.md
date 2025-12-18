# KSAT Prediction Model

## Overview
This project builds an end-to-end machine learning pipeline to predict
**Saturated Hydraulic Conductivity (Ksat)** using soil physical properties.
Ksat is a critical parameter in hydrology, agriculture, and environmental
modeling as it determines how water moves through soil.

The entire workflow is implemented in **one clean, reproducible notebook**
designed to run seamlessly in **Google Colab**.

---

## Dataset
- Source: Soil physical properties dataset
- Size: ~27,000 samples, 35 columns
- Target Variable: **Ksat (Saturated Hydraulic Conductivity)**
- Units standardized to **cm/hr**

### Key Features Used
- Sand (%)
- Silt (%)
- Clay (%)
- Bulk density
- Organic carbon
- Coarse fragments (%)
- Soil texture fractions
- Measurement method


---

## Methodology
The notebook follows a structured pipeline:

1. **Data Cleaning & Preprocessing**
   - Unit standardization
   - Invalid value removal
   - Missing value imputation
   - Categorical encoding

2. **Exploratory Data Analysis**
   - Correlation analysis
   - Feature distributions
   - Heatmaps and summary statistics

3. **Feature Selection**
   - Permutation importance using Random Forest
   - Selection of top predictive features

4. **Model Training**
   - Random Forest Regressor
   - LightGBM Regressor
   - CatBoost Regressor
   - Histogram-Based Gradient Boosting

5. **Evaluation**
   - Root Mean Squared Logarithmic Error (RMSLE)
   - R² Score
   - Robustness testing across multiple subset sizes

---

## Results
| Model        | RMSLE | R² |
|-------------|------:|---:|
| Random Forest | ~0.65 | ~0.58 |
| LightGBM     | ~0.88 | ~0.46 |
| CatBoost     | **~0.65** | **~0.58** |
| HGB          | ~0.67 | ~0.56 |

**CatBoost** achieved the best overall performance, demonstrating strong
generalization and stability across different training sample sizes.

---

## How to Run
1. Open `KSAT_Model_End_to_End.ipynb` in Google Colab
2. Upload the dataset or mount Google Drive
3. Run all cells sequentially

---

## Tools & Libraries
- Python
- Pandas, NumPy
- Scikit-learn
- CatBoost
- LightGBM
- Matplotlib, Seaborn

---

## Conclusion
This project demonstrates a robust, interpretable, and scalable approach
to predicting soil hydraulic conductivity using ensemble machine learning
models. The results highlight the effectiveness of CatBoost for tabular
environmental data with complex feature interactions.




