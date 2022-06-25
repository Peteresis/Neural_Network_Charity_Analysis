<p align="center">
 <img src="https://user-images.githubusercontent.com/98360572/175720732-67aae5c5-96f7-4605-bd5b-24f41884a8b8.png" width="50%" height="50%">
</p>

# Charity Organizations Analysis Using Neural Networks

---
# :one: Overview.

The purpose of this exercise is to develop, with the use of neural networks, a binary classifier that is capable of determining whether or not a particular application would be successful in obtaining funding from a charitable organization known as ##Alphabet Soup##.

We were given a CSV file by the business team at Alphabet Soup that included the names of more than 34,000 groups that have been successful in obtaining funding throughout the years. The dataset has a number of columns, each of which captures a different piece of metadata pertaining to one of the organizations.

---
# :two: Results.

The columns of the data set are:

* `EIN` and `NAME` — Identification columns
* `APPLICATION_TYPE` — Alphabet Soup application type
* `AFFILIATION` — Affiliated sector of industry
* `CLASSIFICATION` — Government organization classification
* `USE_CASE` — Use case for funding
* `ORGANIZATION` — Organization type
* `STATUS` — Active status
* `INCOME_AMT` — Income classification
* `SPECIAL_CONSIDERATIONS` — Special consideration for application
* `ASK_AMT` — Funding amount requested
* `IS_SUCCESSFUL` — Was the money used effectively

## Data Preprocessing

* **What variable(s) are considered the target(s) for your model?**

<p align="center">
 <img src="https://user-images.githubusercontent.com/98360572/175748463-2d59b516-a27a-43fe-afdb-692898415a6d.png" width="50%" height="50%">
</p>

Target, T, is the correct or desired value for the response associated to one input, X. This value will be compared with the output (the response from the neural network), Y to guide the learning process involving the weight changes. The difference between the desired result (the target, T) and the actual output, Y, is the error.  The objective of training the neural network is to minimize the error.

In our case, the objective is that the Neural Network be able to predict if an organization is going to be successful or not, using the funds received, so the `IS_SUCCESSFUL` column contains the target variable. Target variables are also known as dependent variable and we are using this variable to train our model.

* **What variable(s) are considered to be the features for your model?**

Input values are defined as features for the model and are also referred to as independent variables. All the columns in the CSV except the target variable `IS_SUCCESSFUL` and the ones we dropped — `EIN` and `NAME` are included in those variables.


* **What variable(s) are neither targets nor features, and should be removed from the input data?**

The columns `EIN` and `NAME` do not contain data that gives additional information to the model.  They would just add noise to the problem and were therefore removed from the dataset using the `drop` function from Pandas.

In the same way, variables with too many unique values would be removed.  In our example, the column `ASK_AMT` has `8747` unique values, so this variable should also be eliminated, or at least "binned" in order to reduced the number of variables that the model will have to deal with.

But, what is Binning?

Binning is a technique that accomplishes exactly what it sounds like. It will take a column with continuous numbers and place the numbers in “bins” or categories based on ranges that we determine. This will give us a new categorical variable feature.


## Compiling, Training, and Evaluating the Model

### * How many neurons, layers, and activation functions did you select for your neural network model, and why?

A good rule of thumb for a basic neural network is to have two to three times the amount of neurons in the hidden layer as the number of inputs.  In the first run of the model had two hidden layers, the first layer had `80` neurons and the second layer had `30` neurons.  These parameters were changed in subsequent runs, but they will be explained later on.

Other parameters used for the first run were the `relu` activation function and the `adam` optimizer. Adam (the name Adam is derived from adaptive moment estimation) is an optimization algorithm that can be used instead of the classical stochastic gradient descent procedure to update network weights iterative based in training data.

The `binary crossentropy` was used as the loss function. Binary crossentropy is a loss function that is used in binary classification tasks. These are tasks that answer a question with only two choices (yes or no, A or B, 0 or 1, left or right). Several independent such questions can be answered at the same time

<p align="center">
 <img src="https://user-images.githubusercontent.com/98360572/175785310-b4334dea-b42a-4eb4-a628-406b32a6cfa2.png" width="75%" height="75%">
</p>

### * Were you able to achieve the target model performance?

In the instructions for this cahllenge it is stated that "The accuracy for the solution is designed to be lower than 75%", so the objective of the exercise is to optimize the Tensorflow model in order to achieve a target predictive accuracy higher than 75%.

### Results of the original run

The code for the original run is in the file [AlphabetSoupCharity.ipynb](https://github.com/Peteresis/Neural_Network_Charity_Analysis/blob/b4fa8fa35662c2f8b255318495f58ae7ea0d0048/AlphabetSoupCharity.ipynb)

#### Settings Original Analysis 

![image](https://user-images.githubusercontent.com/98360572/175398665-fadca32c-33b1-4e88-9597-ce42fd237d8c.png)

#### Results original Analysis

![image](https://user-images.githubusercontent.com/98360572/175398768-7dcd341c-48d6-4ef0-af9d-17effa1e2b80.png)


### * What steps did you take to try and increase model performance?

There were four attempts to improve the model's accuracy. The first three attempts involved changing the activation function, and the fourth attempt involved changing the number of hiden layers and neurons.

---

### Results of the first optimization run - Using TANH as the activation function.

The code for the first optiization run is in the file [AlphabetSoupCharity - Optimized 1.ipynb](https://github.com/Peteresis/Neural_Network_Charity_Analysis/blob/58eb42352e132a513f917c22a1cd78f157699aeb/AlphabetSoupCharity%20-%20Optimized%201.ipynb)

#### Settings of the first optimization run.

![image](https://user-images.githubusercontent.com/98360572/175400603-64fa0b52-59a2-4b07-ac34-b2019b86addb.png)

#### Results of the first optimization run.

![image](https://user-images.githubusercontent.com/98360572/175400796-a1eba6df-f982-4650-b3a7-4514d31b969d.png)

---

### Results of the second optimization run - Using SIGMOID as the activation function.

The code for the second optiization run is in the file [AlphabetSoupCharity - Optimized 2.ipynb](https://github.com/Peteresis/Neural_Network_Charity_Analysis/blob/58eb42352e132a513f917c22a1cd78f157699aeb/AlphabetSoupCharity%20-%20Optimized%202.ipynb)

#### Settings of the second optimization run.

![image](https://user-images.githubusercontent.com/98360572/175407557-a5d13c42-ca87-431d-a12b-fc2482d94f33.png)

#### Results of the second optimization run.

![image](https://user-images.githubusercontent.com/98360572/175407635-44b918dd-d730-443a-8bfe-0e8be276fa91.png)

---

### Results of the third optimization run - Using RELU as the activation function.

The code for the third optiization run is in the file [AlphabetSoupCharity - Optimized 3.ipynb](https://github.com/Peteresis/Neural_Network_Charity_Analysis/blob/184eefa1d61794874d9c8b56de2dd7afa83d0754/AlphabetSoupCharity%20-%20Optimized%203.ipynb)

#### Settings of the third optimization run.

![image](https://user-images.githubusercontent.com/98360572/175421073-c4babfed-4bbe-493d-906d-13bedabc77ad.png)

#### Results of the third optimization run.

![image](https://user-images.githubusercontent.com/98360572/175419659-14f26835-9ba3-4bcb-a3df-4dba13e54e75.png)

---

### Results of the fourth optimization run - Using SIGMOID as the activation function and Adding one extra neuron layer.

The code for the fourth optiization run is in the file [AlphabetSoupCharity - Optimized 4.ipynb](https://github.com/Peteresis/Neural_Network_Charity_Analysis/blob/184eefa1d61794874d9c8b56de2dd7afa83d0754/AlphabetSoupCharity%20-%20Optimized%204.ipynb)

#### Settings of the fourth optimization run.

![image](https://user-images.githubusercontent.com/98360572/175424350-6a8a93b7-790a-4f21-8406-1810fdd1739e.png)

#### Results of the fourth optimization run.

![image](https://user-images.githubusercontent.com/98360572/175424286-9b9110f8-b31a-489e-b54d-d0e8e3defe68.png)

---
# :three: Summary

The following table shows a summary of the results obtained 


| Run #    | Modification made      | Loss and Accurary Obtained |
| ----------- | -----------   | -----------  |
|   0    | Original Run Algorithm | Loss: 0.5711 Accuracy: 0.7254 |
|   1    | Using TANH activation function | Loss: 0.5668 Accuracy: 0.7249 |
|   2    | Using SIGMOID activation function | Loss: 0.5648 Accuracy: 0.7255 |
|   3    | Using RELU activation function | Loss: 0.7064 Accuracy: 0.7247 |
|   4    | Using SIGMOID activation function and<br> + 1 Extra Layer | Loss: 0.5885 Accuracy: 0.7258 |


What is the relationship between the accuracy and the loss in deep learning?: There is no relationship between these two metrics.

Loss can be defined as the difference between the problem's true values and the values predicted by the model. The greater the loss, the greater the magnitude of the data errors.

The number of errors you made on the data can be used to calculate accuracy.

That means:

* A low accuracy and large loss indicates that you made numerous errors on a large amount of data.

* A low accuracy but low loss indicates that you made minor mistakes on a large amount of data.

* A high accuracy with low loss indicates that you made few errors on a small set of data (best case scenario).

The results above show that it was not possible to exceed the level of 75 percent accuracy, even with the original run's settings. The loss results in the five cases presented are dismal. In each case, the loss function is greater than 50%. The REL function performed the worst in this regard, with a loss value of 70.64 percent.

In terms of accuracy, the difference between runs was marginal. The difference between the lowest and highest accuracy is only 0.11 percent `(72.58 % - 72.47 % = 0.11 %)`, indicating that the model was not improved by the changes made.

So, how could the model be improved?

There is no simple answer to this question, but here are some ideas to get started:

- Considering gathering more data.
- Testing additional activation functions like Leaky RELU, Parametric RELU, ELU, Softmax, Swish, GELU, SELU.
- Testing additional loss functions for binary classification like Hinge Loss or Squared Hinge Loss.
- Increasing the number of hidden layers.
- Increasing the number of neurons per layer.

---
# :four: References.

The Rise of Machine Learning, https://courses.bootcampspot.com/courses/1145/pages/19-dot-0-1-the-rise-of-machine-learning

Towards Data Science: Binning for Feature Engineering in Machine Learning, https://towardsdatascience.com/binning-for-feature-engineering-in-machine-learning-d3b3d76f364a

Machine Leraning Mastery: Gentle Introduction to the Adam Optimization Algorithm for Deep Learning, https://machinelearningmastery.com/adam-optimization-algorithm-for-deep-learning/

Peltarion: Binary crossentropy, https://peltarion.com/knowledge-center/documentation/modeling-view/build-an-ai-model/loss-functions/binary-crossentropy

Machine Learning Mastery: Loss and Loss Functions for Training Deep Learning Neural Networks, https://machinelearningmastery.com/loss-and-loss-functions-for-training-deep-learning-neural-networks/


Data Science Stack Exchange: What is the relationship between the accuracy and the loss in deep learning?, https://datascience.stackexchange.com/questions/42599/what-is-the-relationship-between-the-accuracy-and-the-loss-in-deep-learning

Towards Data Science: Activation Functions in Neural Networks, https://towardsdatascience.com/activation-functions-neural-networks-1cbd9f8d91d6

V7 Labs: Activation Functions in Neural Networks [12 Types & Use Cases], https://www.v7labs.com/blog/neural-networks-activation-functions

Machine Learning Mastery: How to Choose Loss Functions When Training Deep Learning Neural Networks, https://machinelearningmastery.com/how-to-choose-loss-functions-when-training-deep-learning-neural-networks/


