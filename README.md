## Comparing-Classifiers
### Classification Modeling using Portuguese Banking Institution Dataset found in UCI ML Repository.
### Logistic Regression, KNN algorithm, Decision Tree, and SVM model

## Business Objective is to identify the best classification model to help the Portuguese Banking Instition detemrine if a client/contact would subscribe to a bank term deposit.
## Data used is showing that there are a total of 17 campaigns that occurred between May 2008 and November 2010 with an 8% success rate that subscribed to a bank term deposit.

## Process:
#### Select the target feature which in this case in whether a person subscribed to a bank term deposit.
#### Scale and encode the transofrmation for all fields available.
#### Split dataset into to training and testing sets.
#### Using the value_counts on target field of "subscribe" in the test dataset, We come to a baseline score .88, which we'll compare the different models to.

## Modeling Comparisons using default classifiers
#### The accuracy score for test dataset is lower when compared to the training set.
#### There is a drop off when it comes to test scores, which is likely due to under fitting the model.
#### Since only looking at the default classifiers, we may not be getting the optional fit as each run may yield different scores.
#### The results are showing that Decision Tree Model run time is the quickest of the models with the highest variance between test and train scores.
#### While that maybe the case, the Logistic Regrssion Model is the best model with the default classifiers yielding the 2nd fastest time, with high score anbd low variance between scores.
### Note that all 4 models beats the baseline score of .88

| model      | train score      | test score      | time      |
|---------------|---------------|---------------|---------------|
| knn | 0.928589 | 0.928589 | 0.928589 |
| logisticregression | 0.911836 | 0.911143 | 3.139655 |
| svc | 0.921700 | 0.911143 | 0.911143 |
| decisiontreeclassifier | 1.000000 | 0.885652 | 0.933519 |

## Improving the Model by hypertuning the classifiers
### The accuracy score for the training and test scores are more closely aligh with little variance. 
### The Decision Tree Model run time is the quickest of the models with high scores, followed by Logistic Regression.
### Note that all 4 models beats the baseline score of .88
| model      | train score      | test score      | time      |
|---------------|---------------|---------------|---------------|
| knn | 0.924219 | 0.904467 | 3.178268 |
| logisticregression | 0.911836 | 0.911143 | 0.617877 |
| svc | 0.921700 | 0.911143 | 0.911143 | 47.991672 |
| decisiontreeclassifier | 0.917420 | 0.915028 | 0.420784 |

## Further evaluating the co-efficient of each values and fields in our data set
#### Here are the top 5 that have a strong relationship to the target field of whether they subscribe or not.
| feature      | coefs      |
|---------------|---------------|
| emp.var.rate | 2.605767 |
| month_mar | 1.893613 |
| duration | 1.207256 |
| cons.price.idx | 1.090576 |
| poutcome_success | 0.903225 |

#### Here are the bottom 5 that have the least relationship to the target field of whether they subscribe or not.
| feature      | coefs      |
|---------------|---------------|
| education_high.school | 0.029129 |
| loan_yes | 0.028688 |
| housing_yes | 0.018401 |
| marital_single | 0.014044 |
| age | 0.003936 |

## Conclusion:
### The Decicion Tree Model have been identified showed to be the most efficient in terms of time and accuracy.
### The Logiistic Regression Model is close in both time and accuracy, which may show to be better as we do more hypertuning of the classifers.

## Recommendation:
### By looking at the fields that have the strongest correlation and affects the target subscribe field, we should ducing on the terms of the bank terms itself such as rate, months, and durations.





