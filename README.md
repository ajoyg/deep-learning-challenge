# Deep Learning Challenge
Build a neural network model for a nonprofit foundation Alphabet Soup to select the applicants for funding with the best chance of success in their ventures.

### Analysis overview:
A non-profit foundation called Alphabet Soup prvides wants to fund applicants, they need help to seelct applicants for funding with the best chance of success in their ventures. Alphabet Soup’s business team, has provided a CSV dataset containing more than 34,000 organizations that have received funding from the team over the years. I will analyze the features provided in a dataset and build neural networks with different optimization that will predict whether the applicant will be successful if funded by Alphabet Soup.

### Results
I will examine the results of 3 different optimizations with nueral networks using a binary classification.
#### Data preprocessing 
1. Variable in the target for the model: IS_SUCCESSFUL (i.e. was the venture successful)
2. Variables in the features for the model: 
APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT
3. Variables removed from the input data becausew they are neither targets not features:
EIN, NAME

Plotting some of the features versus the target variable (IS_SUCCESSFUL) shows they are evenly distributed across successful and unsuccessful ventures.


#### Compiling, training, and model evaluation
1. Model training details:
Model 1: 16 neurons, 2 hidden layers, model accuracy: 72.55%, loss: 55.84%, activation function: relu hidden layers, sigmoid output. Sarted with a simple neural network model with 2 hidden layers to get sense of the model accuracy.
Model 2: 16 neurons, 3 hidden layers, model accuracy: 73.35%, loss: 57.33%, activation function: sigmoid hidden layers and output. Used keras-tuner and 3 activation functions upto 5 layers to determine the model that yielded the highest accuracy.
Model 3: 15 neurons, 3 hidden layers, model accuracy: 73.32%, loss: 54.64% activation function: sigmoid hidden layers and output

2. Model accuracy:
The goal was to design a neural network model with a 75% accuracy. The best accuracy I was able to achieve was 73.35%.

3. Improving the model performance:
I started with a simple 2 layer neural network model with relu as the activation function and a sigmoid output layer. Next I used the keras-tuner with tanh, relu, and sigmoid activation functions to evaluate the model with the highest accuracy. I tried dropping the INCOME_AMT column from the features as well since the column had a data on income ranges, dates and it was sparsely populated, however, there was not much of a difference in the model accuracy. I tried a third model with the sigmoid acitvation function across all the layers of the neural network.

#### Summary
A neural network with 3 hidden layers using a sigmoid activation function yieled a model accuracy of 73.35% closest to the 75% target. to further improve the model accuracy, I recommend the following -
a. Clean the INCOME_AMT column in the feature table, for example transform the date values in the column to 0s.
b. Vary the number of neurons and layers with a sigmoid activation function to get to the 75% model accuracy target.