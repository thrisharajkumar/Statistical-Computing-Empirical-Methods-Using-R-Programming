# Statistical Computing & Empirical Methods Using R Programming

**Course:** Statistical Computing & Empirical Methods  
**Timeline:** October 2024 – December 2024  
**Institution:** University of Bristol  
**Author:** Thrisha Rajkumar

This repository contains coursework for the Statistical Computing & Empirical Methods unit, which blends foundational statistical techniques, empirical data exploration, and predictive modeling using R.

---

## 💡 Project Highlights

### 1. Supervised Learning & Predictive Modelling
- Developed **Decision Tree** and **Random Forest** classifiers for predicting loan approvals
- Addressed missing data, encoded categorical variables, and engineered features
- Tuned models via **grid search** with 10-fold **cross-validation**
- Achieved model performance:  
  - **AUC = 0.7949**  
  - **F1 Score = 0.70**

### 2. Data Wrangling & Exploratory Data Analysis (EDA)
- Cleaned multi-source financial data (13,824 rows, 63 indicators)
- Applied joins, renaming, and statistical grouping by income & region
- Created violin plots, histograms, bar plots, and time series to reveal trends

### 3. Statistical Simulation & Computing
- Estimated λ for exponential distribution using **MLE**
- Bootstrapped 1000 samples to build **confidence intervals**: CI = [0.0191, 0.0207]
- Simulated 100,000 trials of discrete distributions
- Demonstrated **Central Limit Theorem** using 50,000 sample means

---

## 📦 Folder Structure

```
Statistical-Computing-R/
│
├── data/                      # Raw and processed datasets
│   ├── train.csv
│   ├── test.csv
│   └── financial_data.csv
│
├── scripts/                   # Core R scripts
│   ├── decision_tree_model.R
│   ├── random_forest_model.R
│   ├── bootstrap_simulation.R
│   └── clt_visualisation.R
│
├── notebooks/                 # R Markdown reports
│   ├── SectionA_Code_Output.Rmd
│   ├── SectionB_Analysis.Rmd
│   └── SectionC_Methodology.Rmd
│
├── reports/                   # Final PDF submissions
│   ├── Section-A.pdf
│   ├── Section-B-Summative-Assessment.pdf
│   └── Section-C.pdf
│
├── images/                    # Visuals used in analysis
│   ├── loan_status_by_credit.png
│   ├── income_violin_plot.png
│   ├── clt_distribution.png
│   └── auc_roc_curve.png
│
├── setup.txt                  # Installation and usage instructions
└── README.md                  # This file
```

---

## 🛠 How to Run

### Install R packages:

```r
install.packages(c("tidyverse", "rpart", "randomForest", "caret", "boot",
                   "ggplot2", "e1071", "reshape2", "knitr"))
```

### Run models:

```r
# Load loan dataset
train <- read.csv("data/train.csv")

# Decision Tree
library(rpart)
tree_model <- rpart(Loan_Status ~ ., data = train, method = "class")

# Random Forest
library(randomForest)
rf_model <- randomForest(Loan_Status ~ ., data = train, ntree = 100)
```

### Run bootstrapping:

```r
library(boot)
lambda_hat <- function(x, i) 1 / mean(x[i])
boot_data <- rexp(1000, rate = 0.02)
boot_lambda <- boot(data = boot_data, statistic = lambda_hat, R = 1000)
boot.ci(boot_lambda, type = "perc")
```

---

## 📈 Visual Insights

Visuals located in `/images/`:
- Loan approval by credit history
- Violin plots of income
- AUC–ROC curves for model evaluation
- Histogram of sample means for CLT demonstration

---

## 📑 Documentation

| Section | Description |
|--------|-------------|
| **A**  | Code and execution outputs |
| **B**  | Written analysis, EDA findings, model evaluation |
| **C**  | Dataset description, simulation explanation, MLE/bootstrapping |

All reports available in `/reports/`.

---

## 🧠 Skills Demonstrated

- R Programming (Tidyverse, ggplot2, caret, rpart, randomForest)
- Data Wrangling & Relational Joins
- Predictive Modeling (CART, Random Forest)
- Model Tuning & Cross-Validation
- ROC Analysis, Bias-Variance Evaluation
- Statistical Simulation (MLE, CLT, Bootstrapping)
- Reproducible Reporting with R Markdown

---

## 📜 License

This repository is for academic and educational use under the University of Bristol.  
Reuse is permitted with citation of author and coursework context.
