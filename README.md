# Credit_Score_Classification
Banks have a huge quantity of information on their customers, which can enable them to predict their lending behavior. 

# Goal
My goal is to create an intelligent system to classify people according to their creditworthiness, thereby reducing manual work.

# Data sources
The data source can be found on kaggle website with this link : [https://www.kaggle.com/datasets/shivamb/netflix-shows/data](https://www.kaggle.com/datasets/parisrohan/credit-score-classification). 
It consists in two csv files. One with previous cretit score column, that I have used for the training of my model. And a second one without credit-score column, which I have used as exemple for real prédiction.
Each 28 columns contain the following information: 

![image](https://github.com/MichAdeola/Credit_Score_Classification/assets/105505715/f80f10bb-adcb-4ce8-a0c3-bff710d99450)

# Methodology and tools used

![image](https://github.com/MichAdeola/Credit_Score_Classification/assets/105505715/656f5668-396c-4425-8070-625f2d579fed)

# Results
Based on the results obtained throughout the data analysis process, we can make the following observations:

- There was a lot of missing data. I therefore performed an initial cleanup in excel to update the data relating to the same "customer_id", before integrating the dataset in python for further cleanup of misleading values, in order to have consistent data.
- After pre-processing, the numerical variables were standardized, and the categorical variables encoded by different methods.
- Then, I have used 3 distinct methods to select the features I should keep to predict the target "credit score" : 
  - Firstly, I have used the correlation matrix method, for selecting the variables most correlated with the target.  I considered moderate (>|0.3|) and strong (>|0.5|) correlation thresholds with the encoded target variable. The result was 8 variables.
  - Then, to confirm my choice of features, I have used the Recursive Feature Elimination (RFE) method to bring the 8 best features too.
    The comparison between the 8 features of the RFE method and those initially chosen with the correlation matrix, do not all match. Only 4 are similar. 
  - So I have used Dataiku's feature importance graph to highlight the most important variables in relation to the target. 

  Considering the 3 features selection methods, only 7 features are common. Therefore, for my credit scoring prediction, I have used 7 relevant features, which are :

  ![image](https://github.com/MichAdeola/Credit_Score_Classification/assets/105505715/9ff9692d-e1a7-4251-9ec7-7845243f913d)

- I then have trained the model using various methods:  logistic regression and random forest with scikit learn in python, and XGBoost, and SVM (Support Vector Machine) in dataiku. But the method with the best accuracy was the random forest (0.77065). So I deployed the model using this method.
- And I made my prediction on the second dataset, cleaned in the same conditions as the first.

# Next step
- Optimize the hyperparameters of the deployed model, to further improve the model performance. 
