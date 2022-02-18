# Supervised-Learning-HealthcareData
ML to predict Mental Health disease diagnosis 


## Introduction
This repo contains only the source code for applying several machine learning algorithms on a binary classification task. The data is available here: https://www.datafiles.samhsa.gov/dataset/mental-health-client-level-data-2019-mh-cld-2019-ds0001. The first notebook cleans and prepares the data in a presentable format to be easily modeled. The second notebook contains all classifiers and their evaluations accompanied with charts/plots.


A common application of statistical learning techniques is to predict health outcomes using a range of healthcare specific data. This range tends to include demographic, socioeconomic, clinical, genomic data, etc. where researchers seek to gather enough information to build robust systems capable of predicting the onset of a mental illness such as depression. Clinical Depression is characterized as being a “more-severe form of depression, also known as major depression or major depressive disorder” (Hall-Flavin, 2017).

The data contains slightly more than 6 million data points (each representative of a client). Data was recorded by the State Mental Health Agency (SMHA) over a state-defined 12-month reporting period. The dataset contains 40 columns which consist of anywhere from mental health diagnosis reports to the type of facility a patient received services from. It is important to note that only the type of disease is given and not the symptoms or rationale underlying the diagnosis of it. Moreover, the data provides the types of disorders a patient was diagnosed with as well as an identification number for each individual case. A depression report variable is available as well.

## Cleaning and Preprocessing
Preprocessing the data began with truncating the original dataset of more than 6 million rows down to 100,000 rows. We then divide the dataset into 4 subsets. Each subset is divided based on similar characteristics amongst groups of features. Features take on several variable formats. Briefly, columns such as GENDER and VETERAN are binary encoded. Whereas columns like EDUC (education) are ordinal. This means preserving the order of observations is crucial to the data the variable represents. Missing data is accounted for by the original reviewers of the data where missing points were substituted with the value -9. Depending on the data type for a given column (categorical or numerical), missing data was either dropped altogether or replaced with a unique missing token. Visualizing the data required converting the numerical values of the ordinal columns to their string format representation in order to provide important clarity. 

## Results
Implementing an automatic disease diagnosis detection application to accompany healthcare workers can only effectively work if the application is able to identify when a patient actually presents with a disease. Otherwise, missed diagnoses will only make the situation worse for the patient. The primary mission becomes increasing the number of correct disease detections while safely allowing for some false positives. Having a patient seek treatment due to a disease diagnosis is preferable over a patient not seeking treatment at all when in fact they are ill. 

The F-beta score is used as the primary evaluation metric for all classifers. Essentially, the F-beta score minimizes the number of False Negatives (Patients detected as not possessing a disease when in fact they do) by maximizing the Recall score. The first classifier trained and tested on the Mental Health Client-Level Dataset was a Decision Tree classifer without any fine-tuning or Grid parameter search. Decision Trees perform particulary well in this context because these models make little assumptions about the data. A future direction could be training multiple decision trees in an ensemble fashion to aim for stronger performance. In terms of keeping the number of False Negatives to a minimum, the Decision Tree baseline outperformed a Grid-Searched Logistic Regression model as well as a small neural network. The confusion matrix of the Decision Tree optimized for the F-beta score is pictured below. 

<img width="500" alt="Screen Shot 2021-12-13 at 9 54 46 PM" src="https://user-images.githubusercontent.com/63656931/145924637-b3ad468a-76f9-4d2f-89ed-d8f2ab87ac79.png">



