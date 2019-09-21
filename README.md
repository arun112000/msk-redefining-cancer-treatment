# Personalized Medicine: Redefining Cancer Treatment
https://www.kaggle.com/c/msk-redefining-cancer-treatment
## Problem Statement:
To classify every single genetic mutation based on evidence from text-based clinical literature using Machine Learning. 

## Description:
A lot has been said during the past several years about how precision medicine and, more concretely, how genetic testing is going to disrupt the way diseases like cancer are treated.
But this is only partially happening due to the huge amount of manual work still required. Memorial Sloan Kettering Cancer Center (MSKCC) launched this competition, accepted by the <a href="https://nips.cc/Conferences/2017/CompetitionTrack">NIPS 2017 Competition Track</a>,  because we need your help to take personalized medicine to its full potential. Once sequenced, a cancer tumor can have thousands of genetic mutations. But the challenge is distinguishing the mutations that contribute to tumor growth (drivers) from the neutral mutations (passengers). 
Currently this interpretation of genetic mutations is being done manually. This is a very time-consuming task where a clinical pathologist has to manually review and classify every single genetic mutation based on evidence from text-based clinical literature.
For this competition MSKCC is making available an expert-annotated knowledge base where world-class researchers and oncologists have manually annotated thousands of mutations.
We need your help to develop a Machine Learning algorithm that, using this knowledge base as a baseline, automatically classifies genetic variations.


## Dataset:
The dataset can be found at https://www.kaggle.com/c/msk-redefining-cancer-treatment/data.
1. <b>training_variants</b> - a comma separated file containing the description of the genetic mutations used for training. Fields 
are ID (the id of the row used to link the mutation to the clinical evidence), Gene (the gene where this genetic mutation is 
located), Variation (the amino acid change for this mutations), Class (1-9 the class this genetic mutation has been 
classified on) 
2. <b>training_text</b> - a double pipe (||) delimited file that contains the clinical evidence (text) used to classify genetic          
mutations. Fields are ID (the id of the row used to link the clinical evidence to the genetic mutation), Text (the clinical 
evidence used to classify the genetic mutation) 

## Machine Learning Models:
The dataset was imbalanced and that affected the accuracy of the model. I used one hot encoding and target encoding for gene and variation features and TF-IDF(unigrams, bigrams and trigrams) for text data. Naive bayes, logistic regression and linear SVM models were trained using one hot encoding and TF-IDF . Random forest model was trained using target encoding and TF-IDF. All the models were calibrated using Platt scaling.
                                                           
| Classification model | Train log loss | Test log loss | Misclassification |                                                           
|----------------------|----------------|---------------|-------------------|                                                           
|     Naive Bayes      |     0.9818     |     1.4605    |       0.4451      |                                                           
| Logistic Regression  |     0.4438     |     1.045     |       0.3729      |                                                           
|      Linear SVM      |     0.3694     |     1.0818    |       0.3699      |                                                           
|    Random Forest     |     0.1002     |     0.9207    |       0.3293      |                                                           
