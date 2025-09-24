# Improving Customer Targeting Through Predictive Modeling  

![Made with R](https://img.shields.io/badge/Made%20with-R-blue?logo=r)  
![License: MIT](https://img.shields.io/badge/License-MIT-green)  
![Status: Complete](https://img.shields.io/badge/Status-Finished-brightgreen)  

---

## Executive Summary  
This project applies **predictive analytics** to improve customer acquisition strategies for **The Insurance Company (TIC)**, using the **CoIL Challenge 2000 dataset** (5,822 customers × 86 variables).  

By testing **Logistic Regression** and **Random Forest**, the study demonstrates how predictive modeling can:  
- Improve **customer targeting** for mobile home insurance.  
- Reduce **marketing acquisition costs** by prioritizing high-probability leads.  
- Provide **data-driven insights** for long-term customer relationship management.  

Key takeaway: **Logistic Regression** provided interpretability for deployment, while **Random Forest** delivered higher predictive accuracy by capturing complex interactions.  

📄 **Full report PDF** → [Improving-Customer-Targeting-Through-Predictive-Modeling.pdf](./Improving-Customer-Targeting-Through-Predictive-Modeling.pdf)  

---

## Project Context  
**Business Challenge**  
- Traditional marketing = high cost + low conversion.  
- TIC needed to identify **which customers are most likely to purchase** mobile home insurance policies.  

**Solution Approach**  
- Apply **predictive modeling** to customer demographic & product ownership data.  
- Compare **Logistic Regression** (interpretable baseline) vs. **Random Forest** (higher complexity).  
- Evaluate models on **accuracy, precision, recall, F1-score, ROC-AUC**.  

---

## Dataset  
- **Source**: CoIL Challenge 2000 (real-world business data).  
- **Size**: 5,822 rows × 86 columns.  
- **Features**:  
  - Demographic (age, household size, income, education).  
  - Product ownership (car, life, home policies).  
  - Purchasing power & socio-economic indicators.  
- **Target**: `CARAVAN` → binary (owns mobile home insurance: 1 = yes, 0 = no).  

---

## Methods  

### Data Preparation  
- Converted categorical/factor variables.  
- Split into 80/20 training vs. testing sets.  
- Addressed severe **class imbalance** (only ~6% policyholders).  

### Algorithms  
1. **Logistic Regression (GLM)**  
   - Probability-based, interpretable, fast to deploy.  
2. **Random Forest**  
   - Ensemble method, improved accuracy, captured nonlinear relationships.  

### Evaluation  
- Metrics: Accuracy, Precision, Recall, F1-score, ROC-AUC.  
- Visuals: Decision trees, feature importance, confusion matrix, ROC curve.  

---

## Results & Insights  

- **Logistic Regression**:  
  - Strong interpretability, useful for pilot deployment.  
  - High **precision (78.1%)**, but low **recall (7.1%)** → missed many true buyers.  

- **Random Forest**:  
  - Better handling of complex feature interactions.  
  - **Feature importance**: Purchasing behavior (PBRAND), demographics (MOSTYPE), car/life insurance ownership (APERSAUT, PPERSAUT), and purchasing power (MKOOPKLA) drove predictions.  

- **Business Value**:  
  - Improved targeting efficiency → fewer wasted marketing efforts.  
  - Actionable insights for segmentation & cross-selling.  
  - Foundation for **CRM integration** and **predictive lead scoring**.  

---

## Key Skills Demonstrated  

- **Predictive Modeling**: Logistic Regression & Random Forest.  
- **Data Wrangling**: Handling imbalanced data, feature engineering, correlation analysis.  
- **Model Evaluation**: Confusion matrices, precision-recall tradeoffs, ROC-AUC.  
- **Business Translation**: Linking analytics results to marketing efficiency & acquisition cost reduction.  
- **Reproducibility**: Structured process with R Markdown, version control in GitHub.  

---

## Reproducibility  

**Environment**: RStudio, R 4.2.1  
**Packages**: `stats`, `randomForest`, `caret`, `ggplot2`  

```r
# Example: Logistic Regression
glm_model <- glm(CARAVAN ~ ., data = train, family = "binomial")
summary(glm_model)

# Example: Random Forest
library(randomForest)
rf_model <- randomForest(CARAVAN ~ ., data = train, ntree = 500, importance = TRUE)
varImpPlot(rf_model)
```

---

## Limitations & Next Steps  

- Severe class imbalance limited recall → explore **SMOTE** or cost-sensitive learning.  
- Add hyperparameter tuning (**grid search, Bayesian optimization**).  
- Deploy models with **PMML** for integration into CRM systems.  
- Pilot test with TIC’s customer data before full-scale deployment.  

---

## License  
Released under the **MIT License**. See [LICENSE](./LICENSE).  

---

## Tags  
`predictive-analytics, logistic-regression, random-forest, insurance, customer-targeting, machine-learning, data-science, coil-challenge, r, marketing-analytics`  
