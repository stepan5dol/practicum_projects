# Choosing the location for the well

## Project Description
Let's say you work for the mining company Glavrosgosneft. We need to decide where to drill a new well. 

The steps for choosing a location are usually as follows:
* In the selected region, characteristics for wells are collected: the quality of oil and the volume of its reserves;
* A model is being built to predict the volume of reserves in new wells;
* Choose wells with the highest value estimates;
* Determine the region with the maximum total profit of the selected wells.

You have been provided with oil samples in three regions. The characteristics for each well in the region are already known. Build a model to determine the region where mining will bring the greatest profit. Analyze the possible profits and risks with the Bootstrap technique.

## Instructions for the implementation of the project

Upload and prepare the data. Explain the procedure.

Train and test the model for each region:

 2.1. Divide the data into training and validation samples in the ratio of 75:25.
2.2. Train the model and make predictions on the validation sample.
 2.3. Save the predictions and correct answers on the validation sample.
 2.4. Print on the screen the average stock of the predicted raw materials and the RMSE of the model.
 2.5. Analyze the results.
 
Prepare to calculate the profit:

3.1. Save all the key values for calculations in separate variables.
 3.2. Calculate a sufficient amount of raw materials for the break-even development of a new well. Compare the volume of raw materials obtained with the average stock in each region. 
 3.3. Write conclusions on the stage of preparing the profit calculation.
 
Write a function to calculate the profit for the selected wells and model predictions:

 4.1. Select wells with maximum prediction values. 
 4.2. Sum up the target value of the volume of raw materials corresponding to these predictions.
 4.3. Calculate the profit for the received volume of raw materials.
 
Calculate the risks and profits for each region:

 5.1. Apply the Bootstrap technique with 1000 samples to find the profit distribution.
 5.2. Find the average profit, the 95% confidence interval and the risk of losses. A loss is a negative profit.
 5.3. Write conclusions: suggest a region for the development of wells and justify the choice.
 
Data description

The exploration data of the three regions are in the files:
`/datasets/geo_data_0.csv. Download dataset`
`/datasets/geo_data_1.csv. Download dataset`
`/datasets/geo_data_2.csv. Download dataset`

`id` — unique well ID;

`f0`, `f1`, `f2` — three signs of points (no matter what they mean, but the signs themselves are significant);

`product` — the volume of reserves in the well (thousand barrels).

## Task conditions:

* Only linear regression is suitable for training the model (the rest are not predictable enough).
* During the exploration of the region, 500 points are explored, from which 200 best ones are selected for development using machine learning.
* The budget for the development of wells in the region is 10 billion rubles.
* At current prices, one barrel of raw materials brings 450 rubles of income. The income from each unit of the product is 450 thousand rubles, since the volume is indicated in thousands of barrels.
* After assessing the risks, you need to leave only those regions in which the probability of losses is less than 2.5%. Among them, the region with the highest average profit is chosen.

Synthetic data: details of contracts and characteristics of deposits are not disclosed.

## Conclusions:
Due to the fact that in the second region there is a strong correlation between the sign of f2 and the volume of production, the prediction in this region turned out to be the most accurate. The rest of the predictions practically do not differ from random ones. The largest predicted volume is in 1 region, 3 practically does not lag behind it, in 2 – a much smaller margin.
The largest indicators in terms of average volume are in 1 and 3 regions, however, they also have a larger spread. There will probably be a greater risk in them, it will need to be calculated and taken into account in the final conclusions. At the same time, all three average stocks are less than the payback threshold. It is necessary to select the best 200 points, not random ones.
The only region showing risks of less than 2.5% is Region 2. It also does not show unprofitability, which makes it the best option. It is necessary to develop 2 regions.

**Risks are estimated properly, task is done.**
The only region showing risks of less than 2.5% is Region 2. It also does not show unprofitability, which makes it the best option. It is necessary to develop second region.
