# Forecasting taxi orders

## Project Description
The company "Chetenkoe taxi" collected historical data on taxi orders at airports. To attract more drivers during peak load, you need to predict the number of taxi orders for the next hour. Build a model for such a prediction.
The value of the RMSE metric in the test sample should be no more than 48.

## Conclusions:
Based on the test results, the Random Forest model is able to predict the number of orders for the next hour.
    
The data was converted to the DateTime Index type, sorted in time order and cleared of omissions. Data analysis showed that there is a trend towards an increase in the number of orders in the future and the similarity of the picture of orders by the hour, which is confirmed by autocorrelation with a lag of 24 hours.
    
Several models were trained and validated, the best of which turned out to be a Random Forest model. During testing, the model showed a high enough result to say that it predicts the number of orders for the next hour optimally for the task.
