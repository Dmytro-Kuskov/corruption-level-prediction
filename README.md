# Corruption Level Prediction

Predicting the level of corruption in a country based on socio-economic factors.  
The project explores how indicators like GDP per capita, press freedom, education, internet use and economic factors relate to corruption levels.  
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

- **Key Insights**:  
  - Corruption is highly dependent with 'general development' of a country  
  - The relationship of the factors with corruption is nonlinear and complicated
  - Corruption has deep roots and is weakly susceptible to temporary changes and economic fluctuations  
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

- Gradient Boosting, XGBoost and Random Forest performed best in terms of F1 and Recall and make less costly mistakes.  
- Logistic Regression provides interpretability but weak performance with dangerous mistakes.  
- Hyperparameter tuning improved performance of Gradient Boosting by ~10%, smaller gains for others.   

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

Licenses:

Political Corruption Index (Our World in Data / V-Dem)
Dataset: Political Corruption Index – V-Dem (processed by Our World in Data)

Citation:
“V-Dem (2025) – processed by Our World in Data. ‘Political Corruption Index – V-Dem’ [dataset]. V-Dem, ‘Democracy report v15’ [original data]. Retrieved September 28, 2025 from https://archive.ourworldindata.org/20250925-233948/grapher/political-corruption-index.html (archived on September 25, 2025).”

License: Creative Commons BY; always credit V-Dem and Our World in Data.

Average Years of Schooling (Our World in Data)
Dataset: Average years of schooling (processed by Our World in Data)

Citation:
Data sourced from “Mean years of schooling,” United Nations Development Programme (UNDP) processed by Our World in Data.
Recommended attribution:
“United Nations Development Programme & Our World in Data. ‘Average years of schooling’ [dataset]. Retrieved from https://ourworldindata.org/grapher/average-years-of-schooling”

License: Open Access, typically Creative Commons BY or equivalent, but check original UNDP terms for re-use.

Corruption Perceptions Index (Our World in Data / Transparency International)
Dataset: Corruption Perceptions Index (processed by Our World in Data)

Citation:
“Transparency International (2025) – processed by Our World in Data. ‘Corruption Perceptions Index’ [dataset]. Retrieved from https://ourworldindata.org/grapher/ti-corruption-perception-index”

License: Creative Commons BY for the Our World in Data curation. Transparency International data: non-commercial personal and educational use permitted; for commercial use contact TI.

GDP per Capita, PPP (World Bank)
Dataset: GDP per capita, PPP (constant 2017 international $)

Citation:
“World Bank. ‘GDP per capita, PPP (constant 2017 international $)’ [indicator: NY.GDP.PCAP.PP.KD]. Retrieved from https://data.worldbank.org/indicator/NY.GDP.PCAP.PP.KD”

License: Creative Commons Attribution 4.0 International (CC BY 4.0), World Bank Open Data.

Consumer Price Index / Inflation (World Bank)
Dataset: Inflation, consumer prices (annual %)

Citation:
“World Bank. ‘Inflation, consumer prices (annual %)’ [indicator: FP.CPI.TOTL.ZG]. Retrieved from https://data.worldbank.org/indicator/FP.CPI.TOTL.ZG”

License: Creative Commons Attribution 4.0 International (CC BY 4.0), World Bank Open Data.

Unemployment by Country (World Bank)
Dataset: Unemployment (World Bank)

Citation:
“World Bank. ‘Unemployment by country’ [DataBank dataset, id/f407e65c]. Retrieved from https://databank.worldbank.org/data/Unemployment-by-country/id/f407e65c”

License: Creative Commons Attribution 4.0 International (CC BY 4.0), World Bank Open Data.

World Bank Data Report (GDP and Components)
Dataset: GDP and its breakdown at current prices in US Dollars, DataBank, World Bank

Citation:
“World Bank. ‘GDP and its breakdown at current prices in US Dollars’ [DataBank report]. Retrieved from https://databank.worldbank.org/reports.aspx?ReportId=163203&Type=Table”

License: Creative Commons Attribution 4.0 International (CC BY 4.0), World Bank Open Data.

Internet Usage (% of population) (World Bank)
Dataset: Individuals using the Internet (% of population)

Citation:
“World Bank. ‘Individuals using the Internet (% of population)’ [indicator: IT.NET.USER.ZS]. Retrieved from https://data.worldbank.org/indicator/IT.NET.USER.ZS”

License: Creative Commons Attribution 4.0 International (CC BY 4.0), World Bank Open Data.

Press Freedom Index (World Bank / Reporters Without Borders)
Dataset: Press Freedom Index (World Bank Data360, RWB_PFI)

Citation:
“Reporters Without Borders, World Bank. ‘Press Freedom Index’ [RWB_PFI dataset]. Retrieved from https://data360.worldbank.org/en/dataset/RWB_PFI”

License: Usually Creative Commons BY (World Bank). Data source Reporters Without Borders – may have own terms; check for non-commercial restrictions.

