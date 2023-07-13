# Employee Efficiency Analysis

## Project Overview

The data science project initiated by INX Future Inc aims to analyze the current employee data and identify the root causes behind the declining employee performance indexes. With over 15 years of global business presence and a reputation as one of the top 20 best employers for the past 5 years, INX is committed to maintaining its employee-friendly policies and attracting top talent. However, recent escalations in service delivery and a decrease in client satisfaction levels have raised concerns among top management.

By applying data science techniques and exploring employee data, the project seeks to uncover patterns, trends, and potential correlations that contribute to performance issues. The findings will help INX understand the key factors impacting employee performance and enable them to implement strategies to address these challenges effectively. The ultimate goal is to improve overall performance, enhance client satisfaction levels, and maintain INX's reputation as a leading data analytics and automation solutions provider.


## Table Of Contents
* Business Objective
* Data Understanding
* Data Preprocessing
* Data Visualization
* Machine Learning Model
* Summary
## Business Objective

1. Identify the root causes of the declining employee performance indexes.
2. Analyze the department-wise performance to uncover patterns and correlations related to performance issues.
3. Provide valuable insights and recommendations to the management team for addressing the performance challenges.
4. Improve overall employee performance and productivity.
5. Enhance service delivery to meet client expectations and satisfaction.
6. Minimize the impact on employee morale while addressing non-performance issues.

## Data Understanding

The given data of employees has the 1200 data to perform a higher-level machine learning where it is well structured. The features present in the data are 28 in total. The Shape of the data is 1200x28. The 28 features are classified into quantitative and qualitative where 16 features are qualitative and 11 features are quantitative. The employee ID data is alphanumerical data which doesn't play a role as a relevant feature for performance rating.

The dataset is completely labelled data and categorical which decides the machine learning algorithm to be used. The important aspects of the data are depending on the correlation of data between features and performance rating.

The features present in the data are divided into numerical and categorical data.

### Categorical Features

* Gender
* EducationBackground
* MaritalStatus
* EmpDepartment
* EmpJobRole
* BusinessTravelFrequency
* EmpEducationLevel
* EmpEnvironmentSatisfaction
* EmpJobInvolvement
* EmpJobLevel
* EmpJobSatisfaction
* OverTime
* EmpRelationshipSatisfaction
* EmpWorkLifeBalance
* Attrition
* PerformanceRating

### Numerical Features

* Age
* DistanceFromHome
* EmpHourlyRate
* NumCompaniesWorked
* EmpLastSalaryHikePercent
* TotalWorkExperienceInYears
* TrainingTimesLastYear
* ExperienceYearsAtThisCompany
* ExperienceYearsInCurrentRole
* YearsSinceLastPromotion
* YearsWithCurrManager

### Alphanumeric Features

* Employee ID number 
## Data Preprocessing 

### Handling Missing Values
No missing values were found in the data. 

### Treating Outliers 
`Boxplot` method was used to detect outliers in numerical features.
Capping and flooring method was used to treat outliers. 

### Conversion of categorical features into numerical features
* Label encoding was used for features like `Gender`, `Attrition`, `Overtime`, and `Marital Status`.
* Frequency encoding was implemented for other categorical features since their count had some dependency on the target variable.

### Feature Transformation
In Exploratory Data Analysis Two features were found to be highly positively skewed. *Square root transformation* was used to transform skewed data into less skewed data. 

### Feature Scaling 
Standardization was used to scale features with varying degrees of magnitude.

Standardization is the process of scaling the feature, it assumes the feature follows a normal distribution and scales the feature between mean and standard deviation, here mean is 0, and the standard deviation is always 1.

## Feature Selection

Principal Component Analysis : (PCA) was used to reduce the dimension of the data, Data was having a total of 27 features after dropping a unique and constant column, and from PCA 23 features were able to explain 100% variability. We will consider 90% explained variability and consider 13 principal components.

### Balancing Target Variable
SMOTE: Synthetic Minority Oversampling Technique is one of the most commonly used oversampling methods to solve the imbalance problem. It aims to balance class distribution by randomly increasing minority class examples by replicating them.
SMOTE synthesizes new minority instances between existing minority instances.

## Data Visualization

`Lineplot`, `Barplot`, and `Countplot` were used for univariate and bivariate analysis to visualize various features with the target variable. Some of the relevant findings are as follows:

Numerical features: 
* The age distribution is starting from 18 to 60 where most of the employees are lying between 30 to 40 age count.
* The distance from home to office is distributed from 0 units to 30 units which can be kilometers or miles. Most of the employees are coming from the range of 0 to 5 units.
* Employees worked in multiple companies up to 8 companies where most of the employees worked up to 2 companies before getting to work here.
* The hourly rate range is 65 to 95 for the majority of employees who work in this company.
* In General, Most of the Employees work for up to 5 years in this company.
* Most of the employees get 11% to 15% of salary hikes in this company.

Categorical Features:
* The Gender variance is divided by 60% of Male employees and 40% of Female employees in the company.
* The number of educational backgrounds present in the employees is six unique backgrounds.
* nineteen unique employee job roles are present in this company.
* most of the employees are having an education level of 3
* The Job satisfaction level in this company is a high level for the majority of employees.
* The 85% of employees are not having attrition in their work
only 11% of employees in the company achieved level 4 - performance rating
* The overall percentage of employees doing overtime is 30%



## Machine Learning Model

The machine learning models used in this project are

1. Support Vector Machine classifier
2. Random Forest classifier
3. Artificial Neural Network (MultiLayer Perceptron Model)

All the above-mentioned machine learning algorithms are best for classification and labeled data. The train and test data are divided and fitted into the model. 

* Support vector machine performed well on training data with an accuracy of 95.32% but the test score is 93.52 after applying Hyperparameter tunning score is 95.61 means the model is overfit.
* Random forest very well perform in training data with 100% accuracy but in testing 94.67% after doing hyperparameter tunning testing score is 93.90% which indicates overfitting.
* Artificial neural network[Multilayer percepton] performs very well on training data with 99.14% accuracy and the testing score is 94.28%. So we are selecting the Artifical neural network [Multilayer percepton] model.
## Summary

 The machine learning model has been fitted and predicted with the accuracy score. The goal of this project is nothing but the results from the analysis and machine learning model.

### Goal 1: Department-wise performances
In department-wise performance, we have to analyze the data from each department present in the category. The data frame has to be separated or sliced according to the department wise. In the Employee Department feature, there are six departments available. The performance analysis by the department is as follows,

Sales: The Performace rating level 3 is more in the sales department. The male performance rating is a little bit higher compared to the female. The total work experience does not count in the performance rating.

Human Resources: The majority of the employees lie under the level 3 performance. The older people are performing low in this department. The female employees in the HR department doing really well in their performance. The total work experience does matter to performance in this department.

Development: The largest number of employees are level 3 performers. Employees of all ages are performing at the level of 3 only. The gender-based performance is nearly the same for both.

Data Science: The highest average of level 3 performance is in data science department. Data science is the only department where fewer level 2 performers. The overall performance is higher compared to all departments. Age does not count as an important factor in their performance. Male employees are doing good in this department. Same to HR, the number of work experience does matter.

Research & Development: The age factor is not deviating from the level of performance here where different employees with different ages are there in every level of performance. The R&D has the good female employees in their performance.

Finance: The finance department's performance is exponentially decreasing when age increases. The male employees are doing good. The experience factor is inversely related to the performance level.

### Goal 2: The Top 3 important features affecting the employee performance
The Random Forest classifier and Gradient boosted classifier in Sklearn also contain very convenient and useful attribute feature importances which tell us which features within our dataset have been given most importance through the ML. The top three important features affecting the performance rating are ordered with their importance level as follows,

1. Employment Environment Satisfaction
2. Employee Salary Hike Percentage
3. Years Since the last Promotion

### Goal 3: A Trained model which can predict the employee performance
The trained model is created using the machine learning algorithm as follows with the accuracy score,

1. Support Vector Classifier: 93.52% accuracy.
2. Random Forest classifier: 94.67% accuracy.
3. Artificial Neural Network [Multilayer percepton]: 94.28% accuracy.

### Goal 4: Recommendations to improve the employee performance
* The overall employee performance can be achieved by employee environment satisfaction. The company needs to focus more on the employee environment.
* The salary hike will give the boost to the employees to perform well financially and psychologically.
* The promotion will help the employees to achieve more performance by giving them the chance to be more responsible and have leadership qualities.
* The experience years in the current role need to be revised while offering employment to the new employees.
* Employee's work-life balance affects the performance rating.
* While recruiting for HR, consider the female candidates where they perform well compared to males.
* The development and data science department is having an overall higher performance compared to the rest of the departments.
## Tech Stack

This data analytics project utilizes the following technologies and tools:

- Programming Languages: Python
- Data Analysis Libraries: Pandas, NumPy, Scipy, pylab, Sklearn,  Pickle
- Data Visualization: Matplotlib, Seaborn
- Other Tools: Jupyter Notebook, Git
