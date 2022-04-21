## **Project Introduction**

In this project, I'll be trying to detect fraudulant transactions from a financial dataset containing over 6 million records of transactions. The dataset is extremely imbalanced with the minority(fraud) proportion of just 0.129 % of the total number of records. We will be trying to implement various measures to tackle the challenges and arrive at an acceptable fraud detection performance. For our evaluation metric, we will not be using the commonly used accuracy and ROC AUC but instead we will be using the Precision-Recall AUC. This is because since our data is extremely imbalanced and our objective is to evaluate the detection rate, we need a metric that focusses on the recall and precision rates of the classes.


## **Project Overview**

- Built a model to detect fraudulant transactions from a extremely imbalanced financial dataset with minority(fraud) proportion of just 0.129 %.
- Cleaned, explored and manipulated the entire data extensively on Python to make it usable for our use case.
- Investigated the data and engineered new features as and when necessary in accordance with our project requirements.
- Was able to achieve a near perfect accuracy with Precision-Recall AUC of 98.55 % on the testing set.
- Applied Synthetic Minority Over-sampling Technique (SMOTE) and other measures to overcome extreme imbalance before modelling the classifier.



## **Data Investigation & Exploration**

* Discovered average of feature step is more centered in fraud transactions than that in valid transactions. This indicated that fraud transactions generally happened all around the clock whereas valid transactions might have some sort of frequency distribution. We explored this further in detail.
![enter image description here](https://github.com/rishi5565/fraud-detection-imbalanced-dataset/raw/main/EDA%20Images/1.png)
We concluded that fraud transactions happen all throughout the month but valid transactions peaks throughout the first half of the month and then slacks off.

* Next, we explored comparison between fraud and valid transactions throughout the day.
![enter image description here](https://github.com/rishi5565/fraud-detection-imbalanced-dataset/raw/main/EDA%20Images/2.png)
We concluded that fraud transactions happened all throughout the day whereas valid transactions ramps up after the initial hours of the day. This was an interesting finding which we decided to include in our model.

* Transaction types pie chart of valid transactions.
![enter image description here](https://github.com/rishi5565/fraud-detection-imbalanced-dataset/raw/main/EDA%20Images/3.png)
* Transaction types pie chart of fraud transactions.
![enter image description here](https://github.com/rishi5565/fraud-detection-imbalanced-dataset/raw/main/EDA%20Images/4.png)

* Discovered that:
  - Fraud transactions amount is capped at exactly 10 million units whereas valid transactions amount goes all the way upto 92 million units.
  - Mean of fraud and valid transaction amount is way higher than their respective median indicating high presence of outliers.
  - Fraud transaction amounts are generally higher than valid transaction amounts.
 
 * Discovered an error in the transaction amount and the origin and destination balances. We calculated the error amount and added back to the dataset. This helped us tremendously in achieving a better model performance.
 * Discovered that there were very few transactions that started from existing origin accounts but there were quite a lot of transactions that were made to existing destination accounts.
 * Was able to investigate and drop redundant features.
 
 ## **Model Building**

* We label encoded the categorical features.
* We scaled the dataset and split into training and testing sets.
* We applied Synthetic Minority Over-sampling Technique (SMOTE) to balance the classes in our extremely imbalanced dataset. SMOTE is a widely used technique that works by selecting examples that are close in the feature space, drawing a line between the examples in the feature space and drawing a new sample at a point along that line.*

* For our model selection, we decided to use Random Forest Classifier because it is extremely suitable for huge datasets like ours. Also, it is very flexible, easy to understand and performs pretty solid out of the box without much hyper parameter tuning.

## **Evaluation**

* For our evaluation metric, we decided to use Precision-Recall AUC instead of the commonly used metrics such as accuracy and ROC AUC. This is because since our data is extremely imbalanced and our objective is to evaluate the detection rate, we need a metric that focusses on the recall and precision rates of the classes.

* We were able to achieve a near perfect accuracy with Precision-Recall AUC of 98.55 % on the testing set.

* Precision Recall Curve:
![enter image description here](https://github.com/rishi5565/fraud-detection-imbalanced-dataset/raw/main/EDA%20Images/5.png)

* Confusion Matrix:
![enter image description here](https://github.com/rishi5565/fraud-detection-imbalanced-dataset/raw/main/EDA%20Images/6.png)




## **Conclusion**
We were able to build a model from an extremely imbalanced dataset that can detect fraudulent transactions with near perfect accuracy. With this we concluded our project.

Data Source: [Link](https://www.kaggle.com/datasets/rupakroy/online-payments-fraud-detection-dataset)

### [Note]:  _**Please refer to the Project Notebook file for all the detailed in-depth information regarding this project. The above information is just a brief summary of the project.**_

Thank You,

Rishiraj Chowdhury ([rishiraj5565@gmail.com](mailto:rishiraj5565@gmail.com))
