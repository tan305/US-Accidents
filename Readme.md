## Problem Statement
 
On an average around 37 thousand people die of road accidents in US and reducing road accidents is an important public safety challenge. Accidents can be reduced by identifying accident hotspot locations. Occurrence of accidents can be predicted based on the weather conditions, temperature, location, weekday etc. Using our analysis, we plan to find out the most important factors that cause accident.  Another important outcome during any road accident is severity of traffic which depends on the severity of accidents. So, in addition to finding different factors that cause accidents we will also be predicting the severity of accidents using machine learning models.

## Dataset 
 
The dataset is car accidents data for USA with data collected from Feb 2016 to December 2019. The dataset is taken from Kaggle (US car Accidents Feb16-Dec19). It has 2.9 million observations and 49 attributes with both numerical and categorical data. The dataset is for 49 contiguous US states collected through multiple API including 2 APIs which stream real time traffic data. The features can be categorized into geographical features, weather, date-time, POI (point of interest) annotation.  Proposed techniques and data science methodology.

The methodology planned to be followed to solve the problem consists of different stages. The stages include Business Understanding, Data Preprocessing, Exploratory Data Analysis, Feature Engineering, Data Modeling, Model Evaluation, Recommendations and Insights. Business understanding and data preprocessing tasks comprise of data cleaning, imputation of null values using mean/median, transforming data into meaningful variables or combination of variables. Feature engineering to select the most important features in the dataset. Data modeling includes splitting data into train and validation, running different algorithms such as Decision Tree, Random Forest, Gradient Boost and tuning hyperparameters to build best model. Model evaluation using different metrics such as accuracy and AUC/ROC curve to select the best model. Recommendations and insights derived from exploratory analysis and models built to be implemented to solve business problems.
 
 
## Business Questions intended to be analyzed 
 
We can help the government and transport department by providing insights from our analysis to devise strategies for reducing the number of accidents.**
<br>
* Which State and City recorded the maximum number of accidents?
* Which month or year had how many accidents and if there is a trend or a pattern?
* Relationship of environmental factors like weather contributing to accidents.
* Relationship of accident severity with the place it occurred for Ex: traffic signal or a junction.
* Which time of the day has most accidents? 
* Which week of the year has most accidents?


## Feature Engineering

* Dummies were created in order to transform categorical attributes to numerical attributes using One Hot Encoding.  
* Time related features which provide information regarding the start and end time of the accident aren’t very helpful for our analysis. New features such as day of the week and hour of the day were extracted from these existing features. 
* We extracted some of the most important weather conditions from our weather condition column as using the column directly would not have added to the predicting capability of our model. Then we made dummy variables for each of this weather condition to show the weather conditions present during the accident.  
* TMC column had around 25000 missing values. It was an important column that could significantly improve our models. So, we made a new category for these values as we thought it was the best way to impute.  
* Our target variable Severity ranges between 1 and 4. There is an imbalance in the dataset as most of the data points belong to Severity 2 and there are fewer observations with Severity 1. We combine Severity 1 and 2 as 2 to overcome this problem. 

 
 
**Note:We have split the entire dataset into training and validation data, where 80% of the observations is training data and the rest 20% is the validation data. The models are trained using the training data and their performance is evaluated using validation data. The data has been preprocessed for both multiclass and binary classifications.**
 
 
## Handling Imbalance: 

To handle the imbalance in our data, we used oversampling and undersampling technique. For multiclass target, we undersampled the data with severity 2 and oversampled the data with severity 4 to match the number of data points in class 3. In this way, all the classes had the same number of data points and our data was balanced. For binary classification, we undersampled class 0 such that it matched the number of data points in class 1.

## Model Comparison

![Capture](https://user-images.githubusercontent.com/30891813/82270289-4acc0f80-9942-11ea-9a02-6148018239fa.PNG)

## Notebooks

<br>Data Cleaning and Exploratory Data Analysis – Data_Cleaning_EDA.ipynb
<br>String Indexing and One Hot Encoding – StringIndexing_OHE_Conversion.ipynb
<br>Oversampling and Undersampling – Undersampling_Oversampling.ipynb

<br>Models:
<br>Imbalanced Dataset:
<br>Binary Classification:
<br>Logistic Regression – LR_Binary.ipynb
<br>Random Forest, Decision Tree and GBT – RF_DT_GBT_Binary.ipynb
<br>Multiclass Classification:
<br>Logistic Regression – LR_Multiclass.ipynb
<br>Random Forest and Decision Tree– RFDT_Multiclass.ipynb
<br>Balanced Dataset:
<br>Binary Classification:
<br>Logistic Regression, Random Forest, Decision Tree and GBT –
<br>RF_DT_GBT_LR_Binary_Bal.ipynb
<br>Multiclass Classification:
<br>Logistic Regression – LR_Multiclass_Bal.ipynb
<br>Random Forest and Decision Tree– RFDT_Multiclass_Bal.ipynb
