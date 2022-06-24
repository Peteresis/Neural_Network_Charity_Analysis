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
* What variable(s) are considered the target(s) for your model?
* What variable(s) are considered to be the features for your model?
* What variable(s) are neither targets nor features, and should be removed from the input data?
## Compiling, Training, and Evaluating the Model
* How many neurons, layers, and activation functions did you select for your neural network model, and why?
* Were you able to achieve the target model performance?
* What steps did you take to try and increase model performance?



---
# :three: Summary





|   ⚠️ **NOTE: Please click on any image to zoom**     |
| ----------- |




|   #    | Type of Algorithm      | Name of Algorithm |
| ----------- | -----------   | -----------  |
|   1    | Oversampling Algorithm | Naive Random Oversampling |
|   2    | Oversampling Algorithm | SMOTE Oversampling |
|   3    | Undersampling Algorithm | Cluster Centroid |
|   4    | Combination (Over and Under) Sampling Algorithm | SMOTEENN |
|   5    | Ensemble Learner | Balanced Random Forest Classifier |
|   6    | Ensemble Learner | Easy Ensemble AdaBoost Classifier |



```
🔽 Naive Random Oversampling 🔽
```

<p align="left">
<div class="row">
  <div class="column">
    <img src="https://user-images.githubusercontent.com/98360572/173164118-81231084-fd26-4ddf-85cf-c24ffd6267c0.png" width="40%" height="40%">
    <img src="https://user-images.githubusercontent.com/98360572/173163893-3ddda1c9-ed17-4687-a31a-7903f8e0b9b2.png" width="40%" height="40%">
  </div>
</div>
</p>





















# Neural_Network_Charity_Analysis
 With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to help Beks create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.
 
 
 
Settings Original Analysis 

![image](https://user-images.githubusercontent.com/98360572/175398665-fadca32c-33b1-4e88-9597-ce42fd237d8c.png)

Results original Analysis

![image](https://user-images.githubusercontent.com/98360572/175398768-7dcd341c-48d6-4ef0-af9d-17effa1e2b80.png)


Using TANH

Settings Attempt #1

![image](https://user-images.githubusercontent.com/98360572/175400603-64fa0b52-59a2-4b07-ac34-b2019b86addb.png)

Results Attempt #1

![image](https://user-images.githubusercontent.com/98360572/175400796-a1eba6df-f982-4650-b3a7-4514d31b969d.png)



Using SIGMOID

Settings Attempt #2

![image](https://user-images.githubusercontent.com/98360572/175407557-a5d13c42-ca87-431d-a12b-fc2482d94f33.png)

Results Attempt #2

![image](https://user-images.githubusercontent.com/98360572/175407635-44b918dd-d730-443a-8bfe-0e8be276fa91.png)



Using Relu

Settings Attempt #3

![image](https://user-images.githubusercontent.com/98360572/175421073-c4babfed-4bbe-493d-906d-13bedabc77ad.png)


Results Attempt #3

![image](https://user-images.githubusercontent.com/98360572/175419659-14f26835-9ba3-4bcb-a3df-4dba13e54e75.png)


Using SIGMOID and Adding one extra neuron layer

Settings Attempt #4

![image](https://user-images.githubusercontent.com/98360572/175424350-6a8a93b7-790a-4f21-8406-1810fdd1739e.png)


Results Attempt #4

![image](https://user-images.githubusercontent.com/98360572/175424286-9b9110f8-b31a-489e-b54d-d0e8e3defe68.png)

---
# :three: References.

Using Unsupervised Learning to Discover Unknown Patterns, https://courses.bootcampspot.com/courses/1145/pages/18-dot-0-1-using-unsupervised-learning-to-discover-unknown-patterns

Copy Paste Guru: How to fix "ModuleNotFoundError: No module named 'hvplot'", https://copypaste.guru/WhereIsMyPythonModule/how-to-fix-modulenotfounderror-no-module-named-hvplot

Towards Data Science: Get Started: 3 Ways to Load CSV files into Colab, https://towardsdatascience.com/3-ways-to-load-csv-files-into-colab-7c14fcbdcb92

Holoviz, Hvplot: Plotting, https://hvplot.holoviz.org/user_guide/Plotting.html
 
Github: Colab rendering requires reloading extension in each cell #3551, https://github.com/holoviz/holoviews/issues/3551




