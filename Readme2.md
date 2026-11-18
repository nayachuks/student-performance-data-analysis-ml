# Student Performance Prediction Using Linear Regression (From Scratch)

## 1. Project Overview

This project implements linear regression from scratch using Python and NumPy to predict students' final Mathematics grades (`G3`) using their previous academic grades.

The project begins with a single-feature linear regression model using the second-period grade (`G2`). It is then extended to a multiple-feature model using both the first-period grade (`G1`) and second-period grade (`G2`).

The two approaches are compared using validation Mean Absolute Error (MAE), and the selected model is evaluated against a simple mean-prediction baseline.

## 2. Project Objectives

The objectives of this project are to:

- Understand how linear regression works mathematically and computationally.
- Implement a prediction function using NumPy.
- Implement the cost function manually.
- Calculate gradients for model parameters.
- Implement gradient descent to train the model.
- Compare single-feature and multiple-feature regression models.
- Evaluate predictions using Mean Absolute Error.
- Compare the trained model against a simple baseline.

## 3. Dataset

**Source:** [UCI Machine Learning Repository – Student Performance Dataset](https://archive.ics.uci.edu/dataset/320/student+performance)

**File used:** `student-mat.csv`

The Mathematics dataset contains 395 student records and 33 attributes. It describes student performance in two Portuguese secondary schools.

The dataset includes demographic, social, school-related and academic information.

For this project, the selected variables are:

| Variable | Description                      |
| -------- | -------------------------------- |
| G1       | First-period grade               |
| G2       | Second-period grade              |
| G3       | Final Mathematics grade (target) |

The grades are recorded on a scale from 0 to 20.

## 4. Methodology

### 4.1 Data Preparation

The dataset was loaded using Pandas. The Mathematics dataset was separated into input features and the target variable.

The data was divided into training, validation and test subsets.

### 4.2 Single-Feature Linear Regression

The first model uses `G2` to predict `G3`.

The prediction function is:

y_hat = wx+b\


### 4.3 Multiple Linear Regression

The second model uses both `G1` and `G2` to predict `G3`.

Its prediction function is:

G3_hat = w_1G1+w_2G2+b\


### 4.4 Manual Model Implementation

The regression algorithms were implemented manually using NumPy.

The implementation includes:

- Prediction function
- Cost function
- Gradient computation
- Gradient descent
- Cost-history tracking
- Model prediction and evaluation

Scikit-learn was used only for splitting the dataset with `train_test_split`. Its regression estimators were not used to train the models.

### 4.5 Model Evaluation

Mean Absolute Error (MAE) was used to evaluate prediction performance.

The two regression approaches were compared using validation MAE. The selected model was subsequently compared with a mean-prediction baseline on the test subset.

## 5. Experimental Results

### 5.1 Validation Results

| Model                     | Validation MAE |
| ------------------------- | -------------: |
| G1 + G2 Linear Regression |         0.9143 |
| G2-only Linear Regression |         0.8763 |

The G2-only model achieved a slightly lower validation MAE and was selected as the final model.

### 5.2 Final Test Results

| Model                              | Test MAE |
| ---------------------------------- | -------: |
| Mean Baseline                      |   3.6358 |
| Selected G2-only Linear Regression |   1.0878 |

The selected model achieved approximately 70.1% lower test MAE than the mean baseline.

**Evaluation note:** The test subset was examined during an earlier exploratory stage and reused in the final evaluation. Therefore, the reported test result should not be interpreted as an independent estimate from a completely untouched test set.

## 6. Final Trained Model

The selected model uses the second-period grade (`G2`) to estimate the final grade (`G3`).

The learned equation is:

G3_hat = 0.99437769(G2)-0.08057916\


For a student with a second-period grade of 12, the model predicts a final grade of approximately 11.85.

## 7. Tools and Technologies

- Python
- NumPy
- Pandas
- Matplotlib
- Scikit-learn (data splitting only)
- Jupyter Notebook

## 8. How to Run the Project

### Step 1: Clone or download this repository

### Step 2: Install the required libraries

```bash
pip install numpy pandas matplotlib scikit-learn notebook
```

### Step 3: Download the dataset

Download the Mathematics dataset (`student-mat.csv`) from the UCI Machine Learning Repository.

Place the file inside a folder named `data` in the project directory.

The expected location is:

```text
data/student-mat.csv
```

### Step 4: Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `Student_Performance_Linear_Regression_Organized.ipynb` and run the notebook cells.

## 9. Project Limitations

1. The model was developed using one dataset from two Portuguese secondary schools.
2. The model uses previous academic grades and does not consider other factors that may influence student performance.
3. The model has not been externally validated on students from other schools or countries.
4. The test subset was examined during earlier experimentation and reused in the final evaluation.
5. Predictions are estimates and should not be treated as guaranteed examination results.

## 10. Conclusion

This project demonstrates the implementation of single-feature and multiple-feature linear regression from scratch using NumPy.

The exercise provided practical experience in understanding the mathematical foundations of linear regression, implementing gradient descent, comparing predictive models and evaluating their performance using MAE.

## 11. Dataset Reference

Cortez, P. (2008). *Student Performance* [Dataset]. UCI Machine Learning Repository.

[https://doi.org/10.24432/C5TG7T](https://doi.org/10.24432/C5TG7T)

Dataset licence: Creative Commons Attribution 4.0 International (CC BY 4.0).
