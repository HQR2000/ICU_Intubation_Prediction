# ICU Intubation Prediction

![img1](https://github.com/HQR2000/ICU_Intubation_Prediction/blob/main/public/img1.png)

## Content
- [Abstract](#index1)
- [Dataset](#index2)
- [EDA&Data Preprocessing](#index3)
- [Feature Selection Method](#index4)
- [Predictive Models](#index5)
- [Result Analysis](#index6)

## <span id='index1'>Abstract</span>

This project aims at estimating the patient's chance of intubation in the Intensive Care Unit(ICU) based on machine learning models. Before applying the machine learning models for the prediction, an exploratory data analysis is done to gain insights of the dataset. Then data preprocessing and feature selection methods are used to enhance the usability of the dataset. Three machine learning models are then trained for the prediction, including **Logistic Regression**, **Decision Tree** and **Random Forest**. The complete code of the project can be found in `./code/ICU_Intubation_Prediction.ipynb`.

## <span id='index1'>Dataset</span>

The MIMIC(**M**edical **I**nformation **M**art for **I**ntensive **C**are IV) database is a vast repository of de-identified health-related data from more than 40,000 patients who were admitted to critical care units at the Beth Israel Deaconess Medical Center. This database is available free of charge and encompasses a broad range of information, including demographics, vital sign measurements taken at the bedside (approximately one data point per hour), laboratory test results, procedures, medications, caregiver notes, imaging reports, and mortality rates both inside and outside the hospital. The latest complete version of MIMIC-IV dataset can be found [here](https://mimic.mit.edu/#td-block-1)

For this project, we will use a pre-extracted dataset of the MIMIC-IV. It contains totally `36489` patient healthcare records with `60` indicators. The pre-extracted dataset can be found at `./dataset/MIMIC_IV.csv`.

## <span id='index3'>EDA&Data Preprocessing</span>

For this part, I take several steps to look into the basic information of the dataset and applied several methods for data preprocessing.

These several steps include:
1. Check which features are include in the dataset.
2. Check the ratio of the `True` label to `False` label. (From this step, we noticed the dataset is **imbalanced**, therefore oversampling should be applied to the dataset to avoid overfitting)
3. Check the ratio of missing values in each column. (For column with over `80%` missing values, we directly remove it from the dataset since it cannot provide much information for the models)
4. Calculate the correlation between each feature. (Remove columns with over `95%` correlations to reduce the number of features)
5. Use visualizations to check the distribution of each features. (Most of the features are not in normal distribution, which means that it will be better to use median values to replace the missing values instead of using mean values)

## <span id='index4'>Feature Selection Method</span>
To further reduce the number of features used for the training of predictive models, I applied the **Genetic Algorithm** for the feature selection of each predictive model separately. Some important parameters set for the GA is: `population_size = 30`, `generations = 40`.
For each predictive model I recorded the `20` times accuracy score before and after feature selection to compare the performance. Besides, I also generated the confusion matrix of each model to make sure that the oversampling method works properly to help avoid overfitting.

## <span id='index5'>Predictive Models</span>

In this part, we train three predictive models for the prediction:
- Logistic Regression
- Decision Tree
- Random Forest

For each model, I replace the missing values with `mean` and `median` values respectively to create two dataset and train the model based on each dataset. Besides, since in the EDA part we noticed that the data is **imbalanced**, I also applied `SMOTE`(Synthetic Minority Oversampling Technique) to oversample the data to balance the number of `True` label and `False` label.

## <span id='index6'>Result Analysis</span>
