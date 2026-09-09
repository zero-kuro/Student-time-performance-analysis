# Student Performance: Does How Students Use Their Time Matter?

## Overview

This project explores factors associated with students' academic performance, with a particular focus on how time-related behaviours and commitments relate to final grades.

The analysis is divided into two parts:

* **Part A — General Analysis:** Explore the dataset, build a baseline classification model, and identify potentially important predictors of final grades.
* **Part B — Time-Related Analysis:** Focus on study time, sleep, attendance, extracurricular activities, and part-time employment to investigate their relationships with academic performance.

## Dataset

The project uses the **Student Performance and Study Habits Dataset** from Kaggle, containing 1,000 student observations and features including study habits, attendance, previous grades, parental education, and other student characteristics.

`final_grade` (A–F) is used as the prediction target.

`final_exam_score` was excluded from the model after exploratory analysis showed a very strong relationship with `final_grade`, creating a risk of target leakage.

## Approach

The project includes:

* Exploratory data analysis (EDA)
* Missing-value and categorical-data handling
* Statistical testing using a chi-square test of independence
* `ColumnTransformer` and `Pipeline` for reproducible preprocessing
* Logistic Regression
* K-Nearest Neighbours
* Decision Tree
* Random Forest
* 5-fold cross-validation
* Hyperparameter tuning with `GridSearchCV`
* Confusion matrices and classification metrics
* Logistic Regression coefficient analysis

## Key Findings

### General Model

Logistic Regression achieved the strongest performance among the models tested:

* **Mean 5-fold CV accuracy:** 56.9%
* **Test accuracy:** 63.5%

The model performed considerably better on the more common A, B, and C grades than on D and F.

### Time-Related Factors

Study time showed the strongest association with final grades among the measured time-related variables. Attendance also showed a clear positive association, while sleep duration had a weaker relationship.

Part-time employment and extracurricular participation did not correspond to substantial differences in measured study time, sleep, or attendance.

Study time, sleep, and attendance were also almost uncorrelated with one another, providing little evidence of clear trade-offs between these measured variables.

A Logistic Regression model using only time-related features achieved:

* **Mean 5-fold CV accuracy:** 48.75%
* **Test accuracy:** 53%

This suggests that time-related characteristics contain useful predictive information, but do not capture all of the information available in the broader dataset.

## Limitations

* The dataset contains only **1,000 students**.
* Only **12 students received an F**, limiting the model's ability to learn and evaluate this class reliably.
* Part-time employment and extracurricular activities are recorded only as Yes/No variables and do not measure the actual time spent on these activities.
* Other uses of students' time, such as leisure, commuting, and screen time, are not recorded.
* The analysis identifies **associations and predictive relationships, not causal effects**.

## Tools

* Python
* pandas
* NumPy
* Matplotlib
* scikit-learn
* SciPy

## Notebook

The notebook contains the full exploratory analysis, preprocessing decisions, model comparison, hyperparameter tuning, evaluation, and interpretation of results.

## Data Source

harshadapatil31/student-performance-and-study-habits-dataset

