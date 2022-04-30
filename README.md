# Epitope-Prediction
CSC687-R Final Project 

This project is a part of the CSC687-R Statistical Learning Final Project at The University of Miami.

#### -- Project Status: [Completed]

## Project Intro/Objective
The purpose of this project is to predict, using binary classification, whether an amino acid peptide exhibits antibody-inducing activities. The amino acid peptides studied are from the COVID-19, SARS and B-cell antigen.

### Collaborators
* Riya Agrawal
* James Alfano

### Methods Used
* Logistic Regression
* KNN
* Random Forest
* Gradient Boosting Machine

### Technologies
* R 
* MS Office

## Needs of this project

The dataset for this project has been taken from Kaggle: https://www.kaggle.com/futurecorporation/epitope-prediction
The dataset contains three files with no missing values:
input_bcell.csv: this is the main training data. The number of rows is 14,387 for all combinations of 14,362 peptides and 757 proteins.
input_sars.csv: this is also the main training data. The number of rows is 520.
input_covid.csv: this is our target data. There is no label data in columns.

There are 13 variables that we will be considering for classifying the target and the explanation for each is given below:
parent_protein_id : parent protein ID
protein_seq: parent protein sequence
start_position: start position of the peptide
end_position: end position of the peptide
peptide_seq : peptide sequence
chou_fasman: peptide feature, β turn
emini: peptide feature, relative surface accessibility
kolaskar_tongaonkar: peptide feature, antigenicity
parker: peptide feature, hydrophobicity
isoelectric_point: protein feature
aromacity: protein feature
hydrophobicity: protein feature
stability: protein feature and bcell and sars dataset have antibody valence (target value)
target : antibody valence (target value)                                                                 

input_bcell and input_sars files are combined for training and validation, and the input_covid file is used for future prediction (the target value is unknown for the input_covid dataset). The variables which give identity information are not considered for prediction. These variables are:

parent_protein_id (parent protein ID): identifier 
protein_seq (parent protein sequence): sequence name and is unique
start_position (start position of peptide): the unique identifier of start position
end_position (end position of peptide): the unique identifier of the end position
peptide_seq (peptide sequence): sequence name and is unique in nature

## Project Description
The data was first subjected to experimental data analysis to better understand the data by performing statistical analysis and creating visual plots for the data. The first step was to check for missing values and to address it, if present. The next step was to look at a summary/plot of the variables. Check for the presence of outliers and whether the data is balanced. Once the issues were identified they were treated accordingly. 

It was also identified, during the EDA, that the COVID-19 data set does not contain the target value. Thus, evaluation metrics could not be reported for this data set. To combat this, a small holdout set was created from the combined B-cell and SARS dataset to be able to report metrics. The holdout set uses approximately 20% of the available B-cell and SARS data. Specifically, 11,712 samples are used for training and 3,195 samples are used for testing.

Four models were chosen for the classification: logistic regression; k-nearest neighbor (KNN); random forest; and gradient boosting machine (GBM). 
Logistic regression serves as a baseline model. For this project, two KNN classification models were built with different values of k: sqrt(n) and 5 (where n is the number of samples). The random forest model was applied with the optimal value of mtry. The GBM model was also applied.

All the models were first evaluated on the holdout set and then evaluated using cross-validation. The final results reported were after cross-validation.

## Getting Started
1. Clone this repo (for help see this [tutorial](https://help.github.com/articles/cloning-a-repository/)).
2. Raw Data is being kept (https://www.kaggle.com/futurecorporation/epitope-prediction)
3. Data processing/transformation and modelling scripts are being kept (https://github.com/jma375/Epitope-Prediction/blob/main/EpitopePrediction.Rmd)

## Featured Notebooks/Analysis/Deliverables
* Deck (https://github.com/jma375/Epitope-Prediction/blob/main/epitopepredictionslides.pdf)
* Report (https://github.com/jma375/Epitope-Prediction/blob/main/EpitopePredictionPaper.pdf)
* Code (https://github.com/jma375/Epitope-Prediction/blob/main/EpitopePrediction.Rmd)




