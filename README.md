# Pima-Diabetes-Analysis-Pipeline
# Automated Analysis Pipeline: Pima Diabetes Dataset

## Project Overview

For this assignment, I used the Pima Diabetes Dataset to explore how automated analysis pipelines can be used to analyze clinical data and compare different machine learning models. The goal was to better understand how these pipelines work, how they make analytical decisions, and how changes to the code can affect the results.

I was particularly interested in comparing the different models and seeing whether more complex approaches actually performed better. I do not previously have much experience with ML models so this was a particularly useful assignment for me. As the results would indicate, more complex is not necessarily better. It's more about what the data provides you in terms of how a model may be more applicable for a certain set of data.

## Dataset

The Pima Diabetes Dataset includes 768 observations and 9 variables, including age, BMI, glucose, insulin, blood pressure, and diabetes outcome.

The primary outcome was whether a patient has diabetes:

- 0 = No diabetes
- 1 = Diabetes

**Dataset:** `Pima_Diabetes_Dataset.csv`

## Pipeline Modifications

In addition to running the provided code from the original notebook, I made four modifications to expand the analysis:

1. **Class Balance Assessment:** I added code to automatically evaluate whether one diabetes outcome was substantially more common than the other. I thought this was important because class imbalance can affect how we interpret model performance.

2. **Random Forest Model:** I added a random forest model to compare against the existing logistic regression and decision tree models. I wanted to see whether combining multiple decision trees would improve performance. I felt like here I was essentially building off of the decision tree in a sense. 

3. **Automated Model Comparison:** I added a comparison table that evaluates all three models using accuracy, precision, recall, F1 score, and ROC AUC. The code also automatically identifies the model with the highest ROC AUC. 

4. **Model Performance Visualization:** I created a grouped bar chart comparing the models across all five metrics. I thought this made it much easier to see where each model performed well and where it struggled. I chose a grouped bar chart as I felt that this was the easiest way to internalize/visualize the differences in model performance. 

## Results

The automated comparison identified logistic regression as the best-performing model based on ROC AUC (0.836). Random forest had slightly higher accuracy and precision, while the decision tree had substantially higher recall (80.2%).

What stood out to me was that the decision tree identified considerably more patients with diabetes than the other two models, despite having a lower ROC AUC. From a clinical standpoint, I think this is important because missing patients who actually have diabetes could be more concerning than incorrectly identifying someone as having diabetes.

Overall, I think the results demonstrate that the best model really depends on what we are trying to accomplish and which performance metrics we consider most important.

## How to Run the Analysis (Just including this as if I was submitting to other clinicians or a company) 

1. Download the notebook (`.ipynb`) and Pima diabetes dataset (`.csv`) from this repository.
2. Open the notebook in Google Colab.
3. Run the cells in order, starting from the beginning.
4. When prompted, upload the Pima diabetes CSV file.
5. Continue running the notebook to generate the statistical analyses, model evaluations, and visualizations.

**Google Colab Notebook:** https://colab.research.google.com/drive/1aCQdM0GglDwmBedA2_BqyQJ4Tx4rjl-B?usp=sharing

## Software and Libraries

The analysis was completed using Python in Google Colab. The main libraries include:

- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn

## Assumptions and Limitations

One limitation of the Pima dataset is that some clinical variables contain zero values that may actually represent missing data. This is important because how we handle missing values can influence the results of the analysis.

The dataset is also relatively small and represents a specific population, so the findings may not necessarily apply to other patient populations.

Finally, although the models demonstrated reasonable predictive performance, they would require additional validation before being used in a clinical setting. The automated model selection was based on performance in the test dataset, which is useful for this assignment but would not be sufficient for selecting a model in a clinical prediction study.

Overall, this assignment helped me better understand how automated pipelines work and how different analytical decisions can influence the interpretation of clinical data.
