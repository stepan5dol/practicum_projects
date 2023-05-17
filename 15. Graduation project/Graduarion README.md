# Industy
## Intro

In order to optimize production costs, the metallurgical combine LLC "So Temper steel" decided to reduce electricity consumption at the steel processing stage. You have to build a model that predicts the temperature of steel.

## Description of the processing stage

Steel is processed in a metal bucket with a capacity of about 100 tons. In order for the bucket to withstand high temperatures, it is lined with refractory bricks from the inside. The molten steel is poured into a ladle and heated to the desired temperature with graphite electrodes. They are installed in the bucket lid. 

Sulfur is removed from the alloy (desulfurization), the chemical composition is corrected by adding impurities and samples are taken. Steel is alloyed — its composition is changed — by feeding alloy pieces from a hopper for bulk materials or wire through a special tribe apparatus (English tribe, "mass").

Before the first time alloying additives are introduced, the temperature of the steel is measured and its chemical analysis is performed. Then the temperature is increased for a few minutes, alloying materials are added and the alloy is purged with an inert gas. Then it is mixed and measurements are carried out again. This cycle is repeated until the target chemical composition and optimal melting temperature are reached.

Then the molten steel is sent to the metal finishing or enters the continuous casting machine. From there, the finished product comes out in the form of slabs (Eng. *slab*, "slab").

## Data Description

The data consists of files received from different sources:

- `data_arc.csv` — data about electrodes;
- `data_bulk.csv` — data on the supply of bulk materials (volume);
- `data_bulk_time.csv` *—* data on the supply of bulk materials (time);
- `data_gas.csv` — data on gas purging of the alloy;
- `data_temp.csv` — temperature measurement results;
- `data_wire.csv` — data on wire materials (volume);
- `data_wire_time.csv` — data on wire materials (time).

In all files, the `key` column contains the batch number. There may be several lines with the same `key` value in the files: they correspond to different processing iterations.

## Conclusion 
After conducting a research analysis of the data, randomForest, XGBoost, LightGBM, CatBoost and a Neural Network were trained using the Keras library. All models, except the last one, achieved the target metric on both validation and training samples. 

The `CatBoost` model turned out to be the most accurate, but `LightGBM` takes the first place in terms of the ratio of training time and result. 
    
The most important features for the result are the `Energy` spent on heating the contents of the boiler, the `Heating time` of the boiler and the `Initial temperature` of the contents.

## Report
### Which points of the plan were fulfilled and which were not. Why?

**`All the points of the plan were fulfilled.`**

    1. Data analysis was carried out.
    2. Signs are formed and processed.
    3. Several machine learning models have been trained and the best one has been selected.
    4. The signs are analyzed for significance for predicting the final result.
    
### What difficulties have arisen and how have they been overcome?

**`Difficulties on the part of the task:`**

    1. It is not determined which temperature is the target.
    2. The permissible limits of signs (in particular, temperatures) are not specified.
    3. The variable Gas 1 and, in general, the table with the supply of inert gases are not described.
    
***`Solution`: consultation with the team leader and getting answers to the listed questions.***

**Difficulties on the part of signs:**

    1. The signs are divided into several dataframes.
    2. Not all signs were useful.
    3. A significant number of omissions.
    
***`Solution`: Allocation of a key by which a pivot table can be created. Creating features from existing ones that could correlate. Filling in the gaps with possible values.***

**`Learning difficulties:`**

    1. To create a data-appropriate model based on a neural network, a larger computing resource is needed.
    
***`Solution`: So far, there is no solution, since models based on gradient boosting cope with the task.***

### What key steps in solving the problem were highlighted?

    1. Data analysis – for the correct identification of features and processing.
    2. Data processing and training of several models – to identify the best model.
    3. Analysis of the importance of signs – for subsequent analysis by colleagues and solving the target task of the whole group – reducing energy consumption at the enterprise.
    4. Report – to explain the work done and transfer the received data to the next group. 
    
### The final model and its quality

`Model` : CatboostRegressor

`MAE on test sample' : 5.67

`Parameters` : max_depth = 7, learning_rate = 0.01

### Features used during training:

    1. Initial temperature – did not change
    2. Energy – calculated according to the formula
    3. Heating time – calculated as the difference between the start and end of heating
    4. Gas 1 – did not change
    5. Wire 1 – the gaps are filled with zeros
    6. Wire 2 – the gaps are filled with zeros
    7. Bulk 1 – the gaps are filled with zeros
    8. Bulk 3 – the gaps are filled with zeros
    9. Bulk 4 – the gaps are filled with zeros
    10. Bulk 6 – the gaps are filled with zeros
    11. Bulk 10 – the gaps are filled with zeros
    12. Bulk 11 – the gaps are filled with zeros
    13. Bulk 12 – the gaps are filled with zeros
    14. Bulk 14 – the gaps are filled with zeros
    15. Bulk 15 – the gaps are filled with zeros
    
All features have been standardized using `StandardScaler()`

### Selected hyperparameters of the best model: 

`max_depth` = 7

`learning_rate` = 0.01

`random_state` = 100423

### Recommendations for improving the model

    1. Increase the dataset.
    2. Try to train a neural network in conditions of greater productivity.
    3. Try to choose more accurate parameters (however, do not allow retraining).
