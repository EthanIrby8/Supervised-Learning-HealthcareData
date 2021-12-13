# Supervised-Learning-HealthcareData
ML to predict Mental Health disease diagnosis 

This work was done for a Masters level Machine Learning course. 

## Introduction
This repo contains only the source code for applying several machine learning algorithms on a binary classification task. The data is available here: https://www.datafiles.samhsa.gov/dataset/mental-health-client-level-data-2019-mh-cld-2019-ds0001. The first notebook cleans and prepares the data in a presentable format to be easily modeled. The second notebook contains all classifiers and their evaluations accompanied with charts/plots.


A common application of statistical learning techniques is to predict health outcomes using a range of healthcare specific data. This range tends to include demographic, socioeconomic, clinical, genomic data, etc. where researchers seek to gather enough information to build robust systems capable of predicting the onset of a mental illness such as depression. Clinical Depression is characterized as being a “more-severe form of depression, also known as major depression or major depressive disorder” (Hall-Flavin, 2017).

The data contains slightly more than 6 million data points (each representative of a client). Data was recorded by the State Mental Health Agency (SMHA) over a state-defined 12-month reporting period. The dataset contains 40 columns which consist of anywhere from mental health diagnosis reports to the type of facility a patient received services from. It is important to note that only the type of disease is given and not the symptoms or rationale underlying the diagnosis of it. Moreover, the data provides the types of disorders a patient was diagnosed with as well as an identification number for each individual case. A depression report variable is available as well.

## Cleaning and Preprocessing
Preprocessing the data began with truncating the original dataset of more than 6 million rows down to 100,000 rows. We then divide the dataset into 4 subsets. Each subset is divided based on similar characteristics amongst groups of features. Features take on several variable formats. Briefly, columns such as GENDER and VETERAN are binary encoded. Whereas columns like EDUC (education) are ordinal. This means preserving the order of observations is crucial to the data the variable represents. Missing data is accounted for by the original reviewers of the data where missing points were substituted with the value -9. Depending on the data type for a given column (categorical or numerical), missing data was either dropped altogether or replaced with a unique missing token. Visualizing the data required converting the numerical values of the ordinal columns to their string format representation in order to provide important clarity. 

## Results
