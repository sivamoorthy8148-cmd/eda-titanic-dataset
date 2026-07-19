intern id CITS6974
# eda-titanic-dataset

# 🚢 Titanic Survival — Exploratory Data Analysis (EDA)

A basic-level EDA project exploring the classic Titanic passenger dataset to understand which factors were associated with passenger survival.

## 📌 Project Overview

- **Dataset:** 891 Titanic passengers, 12 columns (`data/titanic.csv`)
- **Type:** Exploratory Data Analysis (data cleaning + visualization)
- **Tools:** Python, Pandas, Matplotlib, Seaborn, Jupyter Notebook

## 📁 Project Structure

```
titanic-eda/
├── README.md                     # This file
├── requirements.txt               # Python dependencies
├── data/
│   └── titanic.csv                # Raw dataset
├── notebook/
│   └── titanic_eda.ipynb          # Main analysis notebook
├── images/                        # Exported charts (used in this README)
└── generate_charts.py             # Script used to regenerate the images/ folder
```

## 🧹 Data Cleaning

- Filled missing `Age` values with the median age
- Filled missing `Embarked` values with the most common port
- Created a `Cabin_Known` flag (since `Cabin` is missing for ~77% of passengers)
- Created a `FamilySize` feature (`SibSp` + `Parch` + 1)

## 📊 Key Visualizations

**Overall survival**

![Survival counts](images/01_survival_counts.png)

Only about **38%** of passengers survived.

**Survival by sex**

![Survival by sex](images/02_survival_by_sex.png)

Women survived at a much higher rate than men — consistent with the "women and children first" evacuation policy.

**Survival by passenger class**

![Survival by class](images/03_survival_by_class.png)

1st class passengers survived far more often than 3rd class passengers.

**Age distribution & survival by age**

![Age distribution](images/04_age_distribution.png)
![Age vs survival](images/05_age_vs_survival.png)

Young children had a noticeable survival advantage.

**Fare distribution**

![Fare distribution](images/06_fare_distribution.png)

Fare is heavily right-skewed — most tickets were cheap, with a small number of very expensive fares.

**Survival by embarkation port**

![Survival by embarked](images/08_survival_by_embarked.png)

**Survival by family size**

![Survival by family size](images/09_survival_by_familysize.png)

Passengers traveling with a small family (2–4 members) had better survival odds than solo travelers or very large families.

**Correlation heatmap**

![Correlation heatmap](images/07_correlation_heatmap.png)

`Pclass` shows the strongest negative correlation with survival; `Fare` and `Cabin_Known` are positively correlated — reinforcing that wealth/class was a major factor in survival.

## 🔑 Key Findings

1. Overall survival rate was about **38%**.
2. **Sex** was the single strongest predictor of survival — women survived far more often than men.
3. **Passenger class** mattered a lot — 1st class > 2nd class > 3rd class.
4. **Age** — children had a survival advantage over adults.
5. **Family size** — small families (2–4) fared better than solo travelers or very large families.
6. **Fare / Cabin** — higher fares and known cabins correlated positively with survival.

## ▶️ How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/titanic-eda.git
   cd titanic-eda
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Launch Jupyter and open the notebook:
   ```bash
   jupyter notebook notebook/titanic_eda.ipynb
   ```

## 📈 Possible Next Steps (Intermediate/Advanced)

- Feature engineering (extract titles from names, deck letter from cabin)
- Statistical hypothesis testing (chi-square test for sex/class vs. survival)
- Predictive modeling (logistic regression, random forest) to predict survival

## 📄 License / Data Source

Dataset sourced from the widely-used public Titanic dataset (originally from Kaggle's "Titanic - Machine Learning from Disaster" competition), mirrored at [datasciencedojo/datasets](https://github.com/datasciencedojo/datasets).
