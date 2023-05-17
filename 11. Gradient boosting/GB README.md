# Determining the cost of cars

## Project Description

The service for the sale of used cars "Not beaten, not painted" is developing an application to attract new customers. It will be possible to find out the market value of your car. 
Build a model that knows how to define it. At your disposal are data on the technical characteristics, configuration and prices of other cars.

Criteria that are important to the customer:
* prediction quality;
* model training time;
* the prediction time of the model.

## Data description

The data is in the file /datasets/autos.csv. Download the dataset. 

## Features

`DateCrawled` — date of downloading the questionnaire from the database

`VehicleType` — type of car body

`RegistrationYear` — the year of registration of the car

`Gearbox` — type of gearbox

`Power` — power (hp)

`Model` — car model

`Kilometer` — mileage (km)

`RegistrationMonth` — month of car registration

`FuelType` — fuel type

`Brand` — car brand

`Repaired` — was the car under repair or not

`DateCreated` — date of creation of the questionnaire

`NumberOfPictures` — number of photos of the car

`PostalCode` — postal code of the questionnaire owner (user)

`lastSeen` — the date of the user's last activity

Target feature:

`Price` — price (Euro)

## Conclusions:
The data has been processed, duplicates have been deleted initially, gaps have been filled in or deleted. Variables not related to the analysis have been removed. The data is normalized.
All models (LGBMRegression, XGBoost Regression, CatBoost Regression) except for simple linear regression coped with the learning outcome better than the designated threshold.
LGBM model was tested as it is the most precise and fast one. In test, results are better than the threshold.
