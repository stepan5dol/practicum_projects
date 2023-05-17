# Protection of personal data of clients
## Project Description
You need to protect the customer data of the insurance company "Though the flood". Develop a method of data transformation so that it is difficult to recover personal information from them. Justify the correctness of his work.
It is necessary to protect the data so that the quality of machine learning models does not deteriorate during the conversion. There is no need to select the best model.

## Instructions for the implementation of the project

Download and study the data.

Answer the question and justify the decision. 

The signs are multiplied by a reversible matrix. Will the quality of linear regression change? (It can be re-trained.)

`a. Will change. Give examples of matrices.`

`b. Will not change. Specify how the linear regression parameters are related in the original problem and in the transformed one.`

Propose a data transformation algorithm to solve the problem. Explain why the quality of linear regression will not change.

Program this algorithm by applying matrix operations. Check that the quality of the linear regression from sklearn does not differ before and after the conversion. Apply the R2 metric.

## Conclusion:
Considering that actions are performed on matrices in the formula, it turns out that the values themselves are not important – the relationship between them is important. Thus, encryption by multiplication by a random, predetermined matrix is a suitable method and does not affect the quality of the linear model. At the same time, having an "encryption key", we can always restore the original data by multiplying by the matrix inverse to this key. 

The data has been analyzed. Mathematical identity of the vectors of weights is proved. The encryption method has been developed. The models have been compared – there are practically no differences in the R2 metric. The algorithm of actions has been developed and is generally relatively universal for any dataset of categorical variables.
