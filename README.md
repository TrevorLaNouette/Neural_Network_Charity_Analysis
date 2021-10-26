# Neural_Network_Charity_Analysis

Technical skills used in this project:

- Tensorflow
- Python
- Pandas
- Sklearn

## Overview of the analysis: Explain the purpose of this analysis.

Using the features in the provided dataset help create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, we received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as the following:

EIN and NAME—Identification columns

APPLICATION_TYPE—Alphabet Soup application type

AFFILIATION—Affiliated sector of industry

CLASSIFICATION—Government organization classification

USE_CASE—Use case for funding

ORGANIZATION—Organization type

STATUS—Active status

INCOME_AMT—Income classification

SPECIAL_CONSIDERATIONS—Special consideration for application

ASK_AMT—Funding amount requested

IS_SUCCESSFUL—Was the money used effectively

### This new assignment consists of three technical analysis deliverables and a written report.

Deliverable 1: Preprocessing Data for a Neural Network Model

Deliverable 2: Compile, Train, and Evaluate the Model

Deliverable 3: Optimize the Model

Deliverable 4: A Written Report on the Neural Network Model (README.md)

## Results:
### Data Preprocessing:

What variable(s) are considered the target(s) for your model?

- The target variable in our data was the "IS_SUCCESSFUL" column.

What variable(s) are considered to be the features for your model?

- All other columns besides "IS_SUCCESSFUL" (Used as our target input), "EIN" and "NAME"(Identifier columns that would not aid in prediction and were dropped) were features used to make predictions. We established this when creating our X and y variables.

What variable(s) are neither targets nor features, and should be removed from the input data?

- "EIN" and "NAME" columns were identifier columns that would not aid in prediction and were dropped as such.

### Compiling, Training, and Evaluating the Model
How many neurons, layers, and activation functions did you select for your neural network model, and why?

<img width="814" alt="Define the Model" src="https://user-images.githubusercontent.com/82718969/138935539-a1add819-430f-4d9f-a9fd-08deaada6668.png">

-For the first layer I used 108 as my standard as you should use between 2 and 3 times the number of features you have for your number of neurons. So I multiplied 43 (features) by 2.5 to get 107.5 which rounds to 108. For my second layer I choose 43 as I wanted to have enough neurons to match the features in the data while not having too many for fear of over training to the data. I choose 2 hidden layers as seemed appropriate given the number of parameters in the data to be split into each layer. I expiremented with this later and found lower accuracy yields by increasing the hidden layers. I choose "relu" as this seemed like the best fit for complex non-linear data. I practiced this and other activatons with a few models at the website below before constructing my model.

https://playground.tensorflow.org/#activation=relu&batchSize=10&dataset=spiral&regDataset=reg-plane&learningRate=0.03&regularizationRate=0&noise=0&networkShape=1&seed=0.32654&showTestData=false&discretize=true&percTrainData=50&x=true&y=true&xTimesY=false&xSquared=false&ySquared=false&cosX=false&sinX=false&cosY=false&sinY=false&collectStats=false&problem=classification&initZero=false&hideText=false&discretize_hide=true&regularization_hide=true&learningRate_hide=true&regularizationRate_hide=true&percTrainData_hide=true&showTestData_hide=true&noise_hide=true&batchSize_hide=true

Were you able to achieve the target model performance?

- Within the 3 attempts I was unable to increase the accuracy score to 75% or above. Even in using 8 layers with 108 nodes in each I saw the highest accuracy score of 74% (Not shown in IPYNB) . This score is also highly succeptible to overfitting the model to the data. Additional improvements to the accuracy score could be achieved by removing categories that had little affect on the "IS_SUCCESSFUL" target.

What steps did you take to try and increase model performance?

-attempt 1 : I increased my Epoch's to see if learning attempts would increase the accuracy yield
-attempt 2 : I increased the amount of neurons to 3x in my 1st hidden layer and 2x in my second as this would allow for more variabiity in decerning our target variable.
-attempt 3 : I changed my activation functions from "relu" to "tanh" to see if this would result in a higher accuracy yield.

<B> None of the attempts yielded a higher accuracy rating than the original model I created <B/>

## Summary: 

Additional improvements to the accuracy score could be achieved by removing categories that had little affect on the "IS_SUCCESSFUL" target. This will allow the model to learn better it will be able to focus more directly on data that has more correlation with successful funding.
