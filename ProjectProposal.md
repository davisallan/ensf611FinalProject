# Project proposal for Will It Rain Tomorrow?
Author: Davis Allan, 10016543

## 1. Why: Question/Topic being investigated 2pts
I am interested in gaining some more confidence with machine learning and how machine learning can be used to make weather predictions. Specifically for this project, I will attempting to predict whether it will rain tomorrow or not based on the conditions provided in the dataset
## 2. How: Plan of attack 2pts
I plan to use Lab 3 as a roadmap for this classification task, and where applicable, follow the steps laid out in the lab to solve this binary classification task. Since the dataset has over 10 years of historical data, I am planning to only use the most recent full year of data (2017) so that it is easier to manage, with the option of implementing the rest of the data in the future.

## 3. What: Dataset, models, framework, components 2pts
- Kaggle dataset: https://www.kaggle.com/jsphyg/weather-dataset-rattle-package (24 features, 8466 samples when only using 2017 data)
- Scikit Learn classifiers: Logistic Regression, SVC, Gaussian NB, Random Forest Classifier, Gradient Boosting Classifier