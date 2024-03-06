# Classification-Regression-Trees

## Overview
This project focuses on solving a couple of regression and classification problems using tree-based models, specifically Random Forest and Decision Trees. The regression task predicts estimated shares outstanding, whereas the classification task involves predicting the diagnosis of breast cancer. Additionally, the project explores two key methods for recognizing feature importance: "Mean Decrease in Impurity" (MDI) and "Permutation Feature Importance" (PFI).

## Data Description
Two datasets were used in this project:

- The New York Stock Exchange dataset, used for the regression task. This dataset contains various financial metrics and was used to build a linear regression model to predict estimated shares outstanding.

-The Breast Cancer dataset, used for the classification task. This dataset includes features related to breast cancer diagnoses and was utilized to build a decision tree classifier to predict the diagnosis (benign or malignant).

## Project Structure
The project is structured as follows:

### Data preprocessing:
Very basic EDA done since the purpose here is to explore tree models. basic data cleaning involved dropping unnecessary columns, handling null values, and splitting into features and target variables.

### Model building and evaluation:
Random Forest models were built for the regression task, with hyperparameters like min_samples_split tuned for optimization.
A Decision Tree classifier was developed for the breast cancer diagnosis prediction, including confusion matrix evaluation and tree visualization.

## Feature importance analysis:

#### Mean Decrease in Impurity
MDI, or "Gini importance", is a way to figure out how crucial a feature is in a Random Forest by looking at how much it reduces the tree's confusion or impurity. Basically, it checks how much cleaner each feature makes the decisions in a tree, and then averages this effect out over all the trees in the forest. The idea is that the more a feature helps in making clear splits, especially in parts of the tree with lots of samples, the more important it is considered. But, there's a catch - this method tends to favor features with more categories, so it can be a bit biased.
![Example Image](/mdi.png)

#### Permutation Feature Importance
PFI (Permutation Feature Importance) is a different way to check how important a feature is, but this time by messing with it. After the model's all set up, it mixes up the values of one feature at a time to mess up the link between the feature and the real results. By doing this, it can see how much worse the model performs without the proper order of that feature's data, showing how key that feature was. This method works with any model, which is pretty cool, but it's also a lot more work because you have to run the model many times, once for every single feature.


## Main Highlights and Outcomes

1. Tuning the min_samples_split hyperparameter in the Random Forest model reduced the out-of-sample mean squared error (MSE) from 0.112 to 0.109, indicating reduced overfitting.
The analysis revealed a significant overlap in feature importance as identified by the MDI and PFI methods, with 9 out of the top 10 features being common between them. In contrast, the Lasso model shared only one common feature, showing a distinct difference in feature selection.

2. For the classification task, the Decision Tree model achieved high precision and recall rates, indicating strong performance in identifying both benign and malignant tumors.
The Decision Tree exhibited potential overfitting, indicated by a full growth where each leaf is pure. Variables like perimeter_worst and concave_points_worst appeared frequently, highlighting their importance in the classification.

4. The project concluded that while the Decision Tree performed well (F1 score of 0.92), there might not be a necessity for pruning in this specific dataset context due to its well-balanced nature.
