# SYRIATEL CUSTOMER CHURN
Author: KENNETH KARANJA
![alt text](image.png)

## Project overview
This research employs machine learning algorithms to create a model that can accurately predict which customers will churn based on the information in the dataset. The dataset includes 20 predictor variables, the majority of which relate to client usage habits. The goal variable is 'churn'. Because the goal variable is categorical, classification methods are utilised to develop the prediction model. Recall is used to assess the model's performance.
## Business problem¶
To enhance their income base, telecommunications businesses must attract new consumers while also increasing client retention rates. Syriatel is a mobile telecommunications and data services company established in Damascus, Syria. It has been demonstrated that long-term connections with clients are more effective than attempting to acquire new ones. Churn prediction has thus become a critical component of the company's strategy. The goal of this project is to create a model that accurately predicts which customers are most likely to churn, as well as to determine the key criteria for forecasting customer turnover. Syriatel can thereby prevent customers who are inclined to churn from actually churning.


## Exploratory data analysis
There is a class imbalance issue since the target class has an unequal distribution of observations. 85.51% of the data is False, with 14.49% being True.

![My image](Images/churn.png)

The scaling varies among the traits, and some of them are not regularly distributed. The features will need to be resized and normalised.

![My image](Images/hist.png)

The correlation between most features is really poor.However, there is an exact positive link between total charge and total minutes at different periods. This is to be expected given that the charge for a call is determined by the number of minutes used.Total day minutes, total day fee, and customer service calls show a weak positive link with churn. The other qualities have a minor link with churn (roughly zero).

![My image](Images/corr.png)

## Data preparation for Machine Learning
- To mitigate multicollinearity, columns displaying total charge at different times are eliminated.<br>
- Train-test split: The data is divided into training and testing sets.<br>
- Create dummy variables for category characteristics.

- SMOTE: SMOTE is used to address class imbalance issues by oversampling the minority class with replacement.<br>
The pie chart below depicts the distribution of the target variable after applying SMOTE.<br>
![My image](Images/churn_2.png)


## Modeling
Various models are created using logistic regression, decision tree and random forest algorithms. Hyperparameter tuning is applied to ldecision tree and random forest algorithms.<br>
A pipeline is used to prevent data leakage. Data is scaled in the pipeline.<br>
The image below shows a summary of the models and their performance.
![My image](Images/modeling.png)

## Evaluation
Decision tree with tuned hyperparameters is the model with the best performance. It has the highest recall score. The accuracy and precision scores are above average.<br>
However, the recall score achieved is below the set score of at least 85%.<br>
The feature importance of the best model is shown below.
![My image](Images/feat_importance.png)

## Conclusions and recommendations
The final model for predicting customer turnover is a decision tree with modified hyperparameters.This model produces the fewest number of false negatives.
The most essential features for predicting client attrition include:
- Total day minutes: the total amount of minutes the consumer has spent on calls during the day.

- Total evening minutes: the amount of minutes spent on calls during the evening. - Customer service calls: the number of times the customer called customer service.
- total international minutes: the number of minutes the user has spent on overseas calls.
Syriatel should provide good customer service in order to meet customers' expectations and analyse their interactions. They can then follow up on any positive or negative feedback received.
The more minutes a consumer spends on the phone, the less likely he or she is to churn. The corporation should compare call fee prices to competitors and propose lowering call charges per minute. This can reduce churn among other consumers.

## Next steps
The targeted recall score of 85% is not achieved by the best performing model. There is still some overfitting in the model irregardless of hyperparameter tuning.
The training data size should be increased to reduce overfitting and hence improve model performance.



## Repository Structure
<<<<<<< HEAD

├── Images                                    <- Both sourced externally and generated from code
├── Data                                      <- Both sourced externally and generated from code
├── README.md                                 <- The top-level README for reviewers of this project
├── presentation.pdf                          <- PDF version of project presentation
└── customer_churn.ipynb                      <- Narrative documentation of analysis in Jupyter notebook
