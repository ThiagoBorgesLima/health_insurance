
<img src="https://github.com/ThiagoBorgesLima/health_insurance/blob/master/references/health.jpeg" width="900" height="475"><br>



# Health Insurance All Company

This repository contains all steps based on CRISP-DS process model methodology to build a prediction for classification model for a large insurance company, where they need to select determinated people to contact and sell a auto insurance from a database that they already have clients with health insurance. The data used in this model is available at the [Rossmann Store Sales competition page at Kaggle.](https://www.kaggle.com/datasets/anmolkumar/health-insurance-cross-sell-prediction)

All information below is fictional.



## 1. Business Problem

Insurance All is a company  that sells health insurance, and the working team are thinkink about offer a new car insurance for their clients. They did a survey with around 380 thousand customers to join in this auto insurance last year. All customers answered yes or no about join this insurance and this answers stay saved in a database with anothers customers.
The working team selected 127 thousand customers who had not answered the survey and they want to do a new campaign with this new potentiali customers with phone calls.



## 2. Business Assumptions

Sales Team only can realize 20 thousand phone calls during this campaign period, and now they need to have a great chance to gain this customers on each phone call. So we need to classify the customers about their potential "Yes" to join this insurance and priorize the phone calls from Sales Team for this potential "Yes" customers saving a lot of time and money.



## 3. Solution Strategy

With this kind of problem, they need a report that contains:

**1-** Insights

**2-** What percentage of customers interested in purchasing auto insurance will the sales team be able to contact by making 20,000 calls?

**3-** If the sales team's capacity increases to 40,000 calls, what percentage of customers interested in purchasing auto insurance will the sales team be able to contact?

**4-** How many calls does the sales team need to make to contact 80% of customers interested in purchasing auto insurance?

## Attribute List

![image](https://user-images.githubusercontent.com/85264359/129487323-f322d8c7-d42f-469c-b0e4-47be6d993c7e.png)




## 4. Solution Strategy


**Step 01. Data Description:** The objective is to use statistical metrics to identify outliers in the business scope.

**Step 02. Feature Engineering:** Derive new attributes based on the original variables to better describe the phenomenon to be modeled.

**Step 03. Data Filtering:** Filter rows and select columns that do not contain information for modeling or do not correspond to the business scope.

**Step 04. Exploratory Data Analysis:** Explore the data to find insights and better understand the impact of variables on model learning.

**Step 05. Data Preparation:** Prepare data so machine learning models can learn specific behavior.

**Step 06. Selection of resources:** Selection of the most significant attributes to train the model.

**Step 07. Machine Learning Modeling:** machine learning model training

**Step 08. Hyperparameter Fine Tunning:** Choose the best values for each of the parameters of the model selected in the previous step.

**Step 09. Convert model performance to business values:** Convert model performance to a business result.

**Step 10. Deploy Model to Production:** Publish the model to a cloud environment so that other people or services can use the results to improve the business decision.

**Step 11. Google Sheets:** Creation of google sheets button to show custumer score.


## Top Three Data Insights

H3. The place of residence influences the decision to take out car insurance.
**True Hypothesys** 

H6. People with newer vehicles are more likely to take out car insurance.
**False Hypothesys** 

H8. People without a driver's license tend not to want car insurance.
**True Hypothesys** 



# 5. Machine Learning Model Applied
Tests were performed using the following algorithms:

**KNN Classifier**

**Logistic Regression**

**Random Forest Classifier**

**XGBoost Classifier**

**Extra Trees Classifier**



# 6. Machine Learning Model Performance

|          Model Name          |   Precision at k    |  Recall at k | 
|:----------------------------:|:-------------------:|:------------:|
| Logist Regression Classifier |       0.176473      |    0.00096   |
|   Extra Trees Classifier     |       0.392151      |    0.00214   |
|  Random Forest Classifier    |       0.470588      |    0.00257   |
|    XGBoost Classifier        |       0.509803      |    0.00279   |
|      KNN Classifier          |       0.490196      |    0.00268   |

For this project I choose **KNN Classifier** to learn how to work with the model, and this model have good metrics to continue.



# 7. Business Results after KNN Classifier

Now with a model built, I can answer the questions made by the working product team.

## 1. The most relevant attributes of customers interested in purchasing auto insurance.

|       Features       |  Importance  |  
|:--------------------:|:------------:|
|       Vintage        |     0.273    |
|     Annual Premium   |     0.244    |
|         Age          |     0.165    |
|      Region Code     |     0.105    |
|    Vehicle Damage    |     0.066    |
| Policy Sales Channel |     0.059    |
|  Previoulsy Insured  |     0.057    |
| Vehicle Age < 1 year |     0.013    |

	 
  
<img src="https://github.com/ThiagoBorgesLima/health_insurance/blob/master/references/features_importance.png" width="900" height="475"><br>

I made this classification with the **ExtraTreesClassifier** method.



## 2. What percentage of customers interested in purchasing auto insurance will the sales team be able to contact by making 20.000 calls?


<img src="https://github.com/ThiagoBorgesLima/health_insurance/blob/master/references/knn_cumulative_a.png" width="900" height="475"><br>


**Calls(20000) / Customers(72000) = 27%** ( RED LINE )

A: The percentage of intrested costumers will reach 70% by making 20.000 calls


## 3. And if the sales team capacity increases to 40.000 calls, what percentage of customers interested in purchasing auto insurance will the sales team be able to contact?

 **Calls(40000) / Customers(72000) = 55%** ( GREEN LINE )
 
A: The percentage of intrested costumers will reach 90% by making 40.000 calls
  

## 4. How many calls does the sales team need to make to contact 80% of customers interested in purchasing auto insurance?

**(80%) Interested = (35%) Contact** ( BLUE LINE )

**Contact(0.35) * Customers(72000) = 25000%** 

A: To reach 80% the sales team will have to make 25000 calls



# 8. Conclusions

A classification model can help a lot to gain precision to sell something to someone who has interest. This model can prove that you can achieve 80% of interested people in a database with only 25000 calls, so this company can increase the gains with this kind of economy.
I can put this model in many places to work, like sheets.
You can use this model with a Google Sheets to gain speed with this analysis for example, it is a simple way to use:

<img src="https://github.com/ThiagoBorgesLima/health_insurance/blob/master/references/google_sheet_a.png" width="900" height="475"><br>


Using this Propensity Score option you can Score your database, based on this classification model at :

https://health-insurance-prediction-t.herokuapp.com/



# 9. Next Steps to Improve

Start a second cycle to analyze the problem, seeking different approaches, especially considering to balance this dataset.

Possible points to be addressed in the second cycle:

-**Work with new combinations of features**

-**Balance the dataset**

-**Create a logic inside google script to re-order my table when get the score, ordering it ascendant**

-**Try new models after balance**

-**Work with a more robust method to find the best Hyper parameters for the model**



# Author

Thiago Borges Lima


[<img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>](https://www.linkedin.com/in/thiago-borges-lima-a731115b)

