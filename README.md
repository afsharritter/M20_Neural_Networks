# M20_Neural_Networks
Module 20 Neural Networks

## Overview

In this analysis, a dataset of charitable organizations was used to train and test a neural network with multiple hidden layers. The dataset was preprocessed to reduce the number of categorical variables in the dataset. This was achieved by placing the least-dense categorical variables in each column into an "other" category.

For example, the Application Type column originally had 17 categorical variables. After bucketing, this count was reduced to 9, with application types less than 1000 being combined into the "other" category. 

After initial testing, the dataset required further processing to improve model accuracy and loss metrics. Neural Network models were tested based on the following schema: 

|Test|Parameters|
|---|-----------|
|Original|Original dataset, relu activation|
|Test 1|Bucketed dataset, relu activation|
|Test 2|Reduced dataset, relu activation|
|Test 3|Bucketed dataset, tanh activation|
|Test 4|Reduced dataset, tanh activation|
|Test 5|Bucketed dataset, relu activation, two hidden layers|


## Results

The original neural network was designed with 12 neurons in the first layer and 10 neurons in the hidden layer. Both layers were instantiated using 'relu' activation. This neural network acheived an accuracy score of 0.5102 and loss of 0.7978. See Figure 1; Figure 7: 'nn_model_0'.

![Figure 1]('challenge/analysis/Neural_Network_Model_Loss_Accuracy.png')

The dataset was further processed to ensure that all columns were appropriately balanced before training and testing a new model. Test 1 achieved an accuracy score of 0.7314 and loss of 0.5556. See Figure 2; Figure 7: 'nn_model_1'.

![Figure 2]('/challenge/analysis/Optimized_Neural_Network_Model_1H_Test_1_evaluation_graph.png')


The dataset was then modified to remove 'STATUS' and 'SPECIAL_CONSIDERATION' features, since both columns were highly imbalanced. Test 2 achieved an accuracy score of 0.7255 and loss of 0.5554. See Figure 3; Figure 7: 'nn_model_2'.

![Figure 3]('/challenge/analysis/Optimized_Reduced_Neural_Network_Model_1H_Test_2_evaluation_graph.png')

Since the secondary reduction produced a lower accuracy score than the primary reduction, a new model was instantiated using the primarily reduced dataset from Test 1, and "tanh" activation function. Test 3 achieved an accuracy score of 0.7299 and loss of 0.5555. See Figure 4; Figure 7: 'nn_model_3'.


![Figure 4]('/challenge/analysis/Optimized_Tanh_Neural_Network_Model_1H_Test_3_evaluation_graph.png')

Since this model did not significantly improve loss or accuracy, the secondarily reduced dataset from Test 2 was tested with "tanh" activation. Test 4 achieved an accuracy score of 0.7314 and loss of 0.5567. See Figure 5; Figure 7: 'nn_model_4'.

![Figure 5]('/challenge/analysis/Optimized_Tanh_Reduced_Neural_Network_Model_1H_Test_4_evaluation_graph.png')

Finally, since no models showed significant improvement past 73% accuracy, a new model was created that added an extra hidden layer with 8 neurons to the original model. Test 5 achieved an accuracy score 0.7305 and loss of 0.5573. See Figure 6; Figure 7: 'nn_model_5'.

![Figure 6]('/challenge/analysis/Optimized_Neural_Network_Model_2H_Test_5_evaluation_graph.png')



|Test|Loss|Accuracy|
|----|--------|----|
|Original|0.7978|0.5102|
|Test 1|0.5556|0.7314|
|Test 2|0.5554|0.7255|
|Test 3|0.5555|0.7299|
|Test 4|0.5567|0.7314|
|Test 5|0.5573|0.7305|


![Figure 7]('/challenge/analysis/Loss_Accuracy_Tests.png')

## Summary 

Overall Tests 1 and 4 both achieved the highest accuracy scores of 0.7314, with Test 1 receiving a marginally better loss of 0.5556, compared to Test 4. 

Test 3, using Tanh activation, had the best loss metric.

Unfortunately, none of the tests were able to reach the target accuracy score of 0.75.

I would recommend repeating the tests with a more intensive deep learning model or other activation to see which works best with this dataset. 
