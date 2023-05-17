# Customer outflow

## Project Description
Customers began to leave Beta Bank. Every month. A little, but noticeable. Bank marketers have found that it is cheaper to retain current customers than to attract new ones.
It is necessary to predict whether the client will leave the bank in the near future or not. You are presented with historical data on the behavior of customers and the termination of contracts with the bank. 
Build a model with an extremely large value of the F1-measure. To pass the project successfully, you need to bring the metric to 0.59. Check the F1 measure on the test sample yourself.
Additionally, measure the AUC-ROC, compare its value with the F1-measure.

## Data description

The data is in the file /datasets/Churn.csv (eng. "customer outflow"). Download dataset

### Features

`RowNumber` — index of the row in the data

`CustomerID` — the unique identifier of the customer

`Surname` — last name

`CreditScore` — credit rating

`Geography` — country of residence

`Gender` — gender

`Age` — age

`Tenure` — how many years a person has been a customer of the bank

`Balance` — account balance

`NumOfProducts` — the number of bank products used by the customer

`HasCrCard` — availability of a credit card

`IsActiveMember` — client activity

`EstimatedSalary` — estimated salary

### Target attribute

`Exited` — the fact of the client's departure

## Data output: the data is complete, but there are significant gaps in the Tenure column — how many years a person has been a bank customer. This may complicate the analysis. 
- [x] Perhaps it is worth removing the lines in which this indicator is missing?

There are 7 qualitative variables in the table (one of them is the target – Exited) and 7 quantitative variables. Quantitative variables, such as the RowNumber column number and the subscriber ID (CustomerID) will definitely not be useful in the analysis. The qualitative attribute of the Surname will also not give anything useful to the analysis. There are 5 signs left for analysis. 
According to the imbalance of classes: there is not such a big difference in the number of "positive" and "negative" responses according to the target attribute, so I do not consider it important to do upsampling or downsampling.

In the test sample, the ROC curve and the AUC value also differ significantly from the random indicator, which indicates the quality of the model. The indicators of the model trained on the upsampling example are still lower.

Old conclusions: Conclusion: The model shows itself stably on data that it has not yet seen. The target value has been reached – the model is almost 2% better than the minimum criterion. At the same time, despite the fact that during validation, the model trained on an artificially modified number of examples showed better results, during testing it turned out that it copes worse than the model trained on data without resampling. probably, there is a factor of retraining. 

Conclusion after stratification: the model with class balancing and upsampling on the test sample showed the best result. Also the results after stratification in general are better.
