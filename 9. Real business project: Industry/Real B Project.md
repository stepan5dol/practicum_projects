# Gold recovery prediction

## Project Description

The data is in three files:

`gold_recovery_train_new.csv` — training sample;

`gold_recovery_test_new.csv` — test sample;

`gold_recovery_full_new.csv` — source data.

The data is indexed by the date and time the information was received (the date attribute). The time-adjacent parameters are often similar.

Some parameters are not available because they are measured and/or calculated much later. Because of this, some features that may be in the training sample are missing in the test sample. Also, there are no target features in the test set.

The source dataset contains training and test samples with all the features.

You have raw data at your disposal: they were simply unloaded from the storage. Before you start building a model, check them for correctness according to our instructions.

## Conclusions:

1. *The final result should look like: a model that predicts the recovery coefficient of gold from gold–bearing ore (the final sMAPE is the final feature, must be accurate).*

2. *The task is performed for:
    2.1 learning from a real example of data analysis in business.
    2.2 improvements in production efficiency.*


The enrichment efficiency is calculated correctly, the average error is much less than 1. There are no columns in the test data set showing the content of substances after passing the purification stages. Dates have been converted to the appropriate data type. The omissions are not more than 5%, mainly in the concentration of by–products in the dump tailings. So far, I don't see the point in touching the passes.

The process really works to increase the proportion of gold in the concentrate and reduce the proportion of impurities. The share of gold increases from 14 to 64% on average. However, some of the gold also goes into the "tails" – goes out of the cycle, falling into technological garbage. At the same time, the proportion of lead also increases – it is not filtered out by the filtration process. The proportion of silver at the last stage decreases – most of the silver goes into the dump tails. Sodium silicate, as a depressant, is consumed in the process of tailings removal.
    
Given the high correlation between some signs, it is worth trying two options:

1. reduce the number of signs
2. use alternative regression methods that take into account correlating features:

    2.1 `ridge regression`
    
    2.2 `lasso regression`
    
    2.3 `"elastic network" regression`


After detailed data preprocessing, standardization and screening of correlating variables, it can be said that the elastic net regression model is trained to predict the quality of the gold recovery process after the flotation stage and after two purification stages.
 
 Despite the fact that the elastic network should be resistant to correlating signs, after the reset of the optional part for the predicate of signs, its quality increased. 
 
 When analyzing the data, it turned out that all parts of the initial mixture, except lead, are removed. The proportion of gold increases after each stage of purification, the proportion of silver and depressant fall, lead does not come out of the concentrate. 

 Given that the training rates of models are higher than the median values, the models are poorly trained.

 Despite this, text predicates are below the threshold value. This is most likely due to the fact that the values in the test sample are generally lower than in the training sample.
