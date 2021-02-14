# Neural_Network_Charity_Analysis

## Overview of the analysis: 
A binary classification neural network model was trained and tested on Alphabet Soup charity data in order to attempt to predict whether charity applicants would be successful if funded by Alphabet Soup using Jupyter Notebook, Pandas, SKLEarn, Tensorflow and related libraries.

## Results: 
Results of building the model were as follows:

### Data Preprocessing
- The target variable for this model was the "IS_SUCCESFUL" column which marks "1" as a succesful charity application and "0" as unsuccessful.
- Variables with no use were "NAME" and "EIN" which were dropped from our original DataFrame.
- Feature variables were all remaining variables: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT.

### Compiling, Training, and Evaluating the Model
- Originally, it was decided to add two hidden layers with 80 and 30 neurons. The activation functions selected were ReLu for the hidden layers, and Sigmoid for the output layer. ReLu and Sigmoid activation functions were selected for their commonality amongst Binary Classification models, while the number of hidden layers and neurons were selected as a starting point to a bit arbitrarily in order to begin with experimentation of the NN configuration.
- After several optimization changes, the desired model performance of 75% accuracy was not accomplished.
- An initial accuracy score of .7252 was achieved.
- The first optimization attempt added 3 more hidden layers and 50 more epochs(100 total). This resulted in an approximate .005% decline in accuracy (.7247).
- The second optimization attempt returned to the starting level of hidden layers and epochs(50 total), but reduced the number of features by eliminating "STATUS" and "SPECIAL_CONSIDERATIONS" columns. Also the neurons per each hidden layer were increased. This resulted in an approximate .001% improvement in accuracy (.7262).
- The third optimization attempt combined the first two. This led to the greated increase in accuracy achieved. An approximate .0016% boost from the original test (.7268).
- The fourth optimization attemp kept all properties of the third, but the output layer activation function was changed from "sigmoid" to "tahn". This resulted in an accuracy scored approximately .0011% less accurate than attempt #3 (.7257).


## Summary: 
Overall, the results of the deep learning model achieve an accuracy well above random chance. As the model is trained now, it can predict whether a charity application will be succesful up to 72.68% of the time. Much better than a 50/50 shot!

Of course, when it comes to binary classification, depending on your resources, there are other methods to achieve analysis and predict whether or not an application would be succesful. As taught in the above lesson on Neural Networks, a supervised learning method could also be used to predict a succesful charity or not. Again, using the lesson as reference, it would make sense to use a Random Forest Classifier for this binary classification problem, as it is typically highly accurate and requires less computational power.
