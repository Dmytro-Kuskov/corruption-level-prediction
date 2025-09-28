# Corruption Level Prediction

Predicting the level of corruption in a country based on socio-economic factors.  
The project explores how indicators like GDP per capita, press freedom, education, and inequality relate to corruption levels.  
Goal: test whether machine learning can provide meaningful predictive power and highlight the trade-offs of different models.

---

## Project Overview

- **Problem definition**: Corruption is multi-dimensional and difficult to measure.  
  This project uses publicly available socio-economic data to approximate corruption levels and test predictive models.  

- **Approach**:
  1. Data preprocessing (cleaning, imputation, encoding, scaling, outlier handling).  
  2. Feature engineering and selection (VIF, correlation thresholds).  
  3. Model training (Logistic Regression, Random Forest, Gradient Boosting, SVC, etc.).  
  4. Hyperparameter tuning with GridSearchCV.  
  5. Evaluation using multiple metrics (Accuracy, Precision, Recall, F1, ROC).  

- **Key questions**:  
  - Which socio-economic features correlate most with corruption levels?  
  - How do trade-offs between interpretability and accuracy play out?  
  - Can tuned models achieve ≥5% performance gain over defaults?  
---
## Project Structure
```
project/
│── data/
│   ├── raw/
│   ├── interim/
│   ├── processed/
│
│── notebooks/
│   ├── 01_data_preprocessing.ipynb
│   ├── 02_model_training.ipynb
│
│── reports/
│   ├── Problem_Definition.md
│   ├── Performance Report.pdf
│
│── README.md
│── requirements.txt
```

---

## Results

| Model              | Accuracy | F1-score | Precision | Recall |
|--------------------|----------|----------|-----------|--------|
| RandomForest       | 0.78     | 0.78     | 0.78      | 0.78   |
| LogisticRegression | 0.57     | 0.54     | 0.54      | 0.57   |
| SVC                | 0.65     | 0.64     | 0.66      | 0.65   |
| GradientBoosting   | 0.79     | 0.79     | 0.79      | 0.79   |
| KNeighbors         | 0.70     | 0.70     | 0.71      | 0.70   |
| **XGBoost**            | **0.80**     | **0.79**     | **0.79**      | **0.80**   |

- Gradient Boosting and Random Forest performed best in terms of F1 and Recall.  
- Logistic Regression provides interpretability but weaker accuracy.  
- Hyperparameter tuning improved performance of Gradient Boosting by ~10% (F1), smaller gains for others.  
- Trade-offs: higher recall reduces false negatives (important in corruption context), but sometimes at the cost of precision.  

---

## How to Run

1. Clone the repo:  
   ```
   git clone https://github.com/yourusername/corruption-prediction.git
   cd corruption-prediction
   ```
2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Explore notebooks:

  notebooks/01_data_preprocessing.ipynb → data cleaning, EDA.

  notebooks/02_model_training.ipynb → model training and evaluation.
