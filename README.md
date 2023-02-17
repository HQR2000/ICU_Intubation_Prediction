# ICU Intubation Prediction

## Content
- [Abstract](#index1)
- [Dataset](#index2)

## <span id='index1'>Abstract</span>

This project aims at estimating the patient's chance of intubation in the Intensive Care Unit(ICU) based on machine learning models. Before applying the machine learning models for the prediction, an exploratory data analysis is done to gain insights of the dataset. Then data preprocessing and feature selection methods are used to enhance the usability of the dataset. Three machine learning models are then trained for the prediction, including _Logistic Regression_, _Decision Tree_ and _Random Forest_.

## <span id='index1'>Dataset</span>

The MIMIC(**M**edical **I**nformation **M**art for **I**ntensive **C**are IV) database is a vast repository of de-identified health-related data from more than 40,000 patients who were admitted to critical care units at the Beth Israel Deaconess Medical Center. This database is available free of charge and encompasses a broad range of information, including demographics, vital sign measurements taken at the bedside (approximately one data point per hour), laboratory test results, procedures, medications, caregiver notes, imaging reports, and mortality rates both inside and outside the hospital. The latest complete version of MIMIC-IV dataset can be found [here](https://mimic.mit.edu/#td-block-1)

For this project, we will use a pre-extracted dataset of the MIMIC-IV. It contains totally `36489` patient healthcare records with `60` indicators. The pre-extracted dataset can be found at `./dataset/MIMIC_IV.csv`.

## 
