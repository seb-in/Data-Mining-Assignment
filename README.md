# Data Mining Assignment

[![DP](https://img.shields.io/badge/-Data%20Preparation-blue)](http://blank.org/)
[![DC](https://img.shields.io/badge/-Data%20Classification-orange)](http://blank.org/)
[![P](https://img.shields.io/badge/-Prediction-red)](http://blank.org/)

[![stability-wip](https://img.shields.io/badge/stability-work_in_progress-lightgrey.svg)](https://www.google.com/does_not_exist.jpg%20404)


## Overview 

In this assignment, you will solve a real-world data mining problem. This assignment requires you to understand the theory discussed in the workshops, conduct some research into the data mining problem to solve, and use the skills that you should have developed through completing practical exercises to perform various data mining tasks. 
Please note that this is an individual assignment. Whilst you may discuss general data mining topics related to this assignment with other students, you must make sure that your work is not accessible by anyone else. There are a large number of choices to make and therefore it is very unlikely to have identical submissions by chance. Submissions that are very similar will be investigated for academic misconduct. 

## Problem Description 

In this assignment, you will perform predictive analytics. You are given a CSV data file (data2020.student.csv) which contains a total of 1100 samples. The first 1000 samples have already been categorised into two classes. You are asked to predict the class labels of the last 100 samples associated with IDs from 1001 to 1100. You are given the following information 

* The attribute Class indicates the class label. For each of the first 1000 samples, the class label is either 0 or 1. For each of the last 100 samples, the class label is missing. You are asked to predict these missing class labels. 
* There are exactly 50 samples from each class in the last 100 samples to be predicted. 
* Attributes are either categorical or numeric. Note that some attributes may appear numeric. You will need to decide whether to treat them as numeric or categorical and justify your action. 
* The data is known to contain imperfections: 
    
    - There are missing/corrupted entries in the data set. 
    - There are duplicates, both instances and attributes. 
    - There are irrelevant attributes that do not contain any useful information useful for the classification task. 
    - The labelled data is imbalanced: there is a considerable difference between the number of samples from each class.
 
 Note that the attribute names and their values have been obfuscated. Any pre-processing and analytical steps to the data need to be based entirely on the values of the attributes. No domain-specific knowledge is available.
 Attempt the following: 

* Data Preparation: In this phase, you will need to study the data and address the issues present in the data. At the end of this phase, you will need to obtain a processed version of the original data ready for classification, and suitably divide the data into two subsets: a training set and a test set. 
* Data Classification: In this phase, you will perform analytical processing of the training data, build suitable predictive models, test and validate the models, select the models that you believe the most suitable for the given data, and then predict the missing labels. 
* Report: You will need to write a complete report documenting the steps taken, from data preparation to classification. In addition, you should also give comments or explain your choice/decision at every step. For example, if an attribute has missing entries, you have to describe what strategy taken to address them, and why you employ that particular strategy based on the observation of the data. Importantly, the report must also include your prediction of the missing labels. 

## The Tasks 

### Data Preparation

 In this first task, you will examine the data attributes and identify issues present in the data. For each of the issues that you have identified, decide and perform necessary actions to address it. Finally, you will need to suitably split the data into two sets: one for training and one for testing, the latter contains 100 samples with missing class labels. The two sets must also be submitted electronically with your report. They must be presented in Weka ARFF format. Your marks for this task will depend on how well you identify the issues and address them. Below is a list of data preparation 

* Irrelevant attributes: this data set is known to have irrelevant attributes. - Describe what you think irrelevant attributes are. - For each attribute, carefully examine it and decide whether it is irrelevant. If so, give a brief explanation and remove the attribute. 
* Missing entries - Which attributes/instances have missing entries? - For those attributes/instances, how many missing entries are present? - For each attribute/instance with missing entries, make a suitable decision, justify it, and proceed. 
* Duplicates - Detect if there are any duplicates (instances/attributes) in the original data? - For each attribute/instance with duplicates, make a suitable decision, justify it, and proceed. * Data type: - For each attribute, carefully examine the default data type (e.g. Numeric, Nominal, Binary, String, etc.) that has been decided when Weka loads the original CSV file. - If the data type of an attribute is not suitable, give a brief explanation and convert the attribute to a more suitable data type. Provide detailed information of the conversion. 
* Scaling and standardisation: - For each numeric attribute, decide if any pre-processing (e.g. scaling, standardisation) is required. Explain why it is needed (this should be discussed in relation to the subsequent classification task). 
* Feature/Attribute selection: if applicable, clearly indicate which attributes you decide to remove in addition to those (obviously) irrelevant attributes that you have identified above and give a brief explanation why. 
* Data instances: if you decide to make changes to the data instances with class labels (this may include selecting only a subset of the data, removing instances, randomizing/reordering instances, or synthetically injecting new data instances to the training data, etc. ), provide an explanation. 
* Data imbalance: examine if class imbalance is present and explain why it could be an issue for the prediction. Perform any necessary actions to address class imbalance and justify them. 
* Feature engineering: you may also come up with attributes derived from existing attributes. If this is the case, give an explanation of the new attributes that you have created. 
* Others: describe other data-preparation steps not mentioned above. 
* Training, Validation, and Test Sets: suitably divide the prepared data into training, validation and test sets. These sets must be in ARFF format and submitted together with the electronic version of your report. See the Submission section for further information. 

### Data Classification 

For this task, you will demonstrate convincingly how you select a suitable classification scheme to learn the predictive model from training data and use that model to predict the missing labels. You will also need to estimate the prediction accuracy on the actual test data. Finally, you will need to provide your prediction as a table in the report and a CSV file to be submitted electronically. You will need to demonstrate the following: 

* Classifier selection: you will need to select at least three (3) classifiers that have been discussed in the workshops: k-NN, Naive Bayes, and Decision Trees (J48). Other classifiers, including meta classifiers, are also encouraged. Every classifier typically has parameters to tune. If you change the default parameters to achieve higher cross-validation performance, clearly indicate what the parameters mean, and what values you have selected. 

* Cross validation: you will need to address the following 

    - How to evaluate the effectiveness of a classifier on the given data? 
    - How to address the issue of class imbalance in the training data? 
    - What is your choice of validation/cross-validation? 
    - For each classifier that you’ve selected, what is the validation/cross-validation performance? Give an interpretation of the confusion matrix.
    - For each classifier that you’ve selected, what is the estimated classification accuracy on the actual test data? 

* Classifier comparison: 

    - Compare the classification performance between difference classifiers. You need to select at least two (2) evaluation metrics, for example F-measure and classification accuracy, when comparing them. Your comparison must take into account the variation between different runs due to cross-validation.
    - Based on the comparison, select the best two (2) classification schemes for final prediction. Note that the two classification schemes can be one type of classifier, but with two different parameters. Clearly indicate the final choice of parameters if they are not the default values. 

* Prediction: 

    - Use the best two classification schemes that you have identified in the previous step to predict the missing class labels of the last 100 samples in the original data set. 
    - Provide your prediction in the report by creating a table, the first column is the sample ID, the second and third columns are the predicted class labels respectively. 
    - Produce a CSV file with the name predict.csv that contain your prediction in a similar format: the first column is the sample ID, the second and third columns are the predicted class labels. This file must be submitted electronically with the electronic copy of the report via Blackboard. An example of such a file is given below 