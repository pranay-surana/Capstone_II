# Capstone II : Classification of Potential Customers

## Introduction:

Banks target customers through campaigns and using specific communications.As sending communications to customers results into faliure in subscriptions and if targeting random customers could lead to waste of resource and cost. Therefore, Banks target customers through campaigns and using specific communications.As sending communications to customers results into faliure in subscriptions and if targeting random customers could lead to waste of resource and cost.


## Problem Statement:

To classify the client will subscribe a bank term deposit or not for future campaign, to identify success of Bank Telemarketing

## Data

The data is related with direct marketing campaigns of a Portuguese banking institution. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required, in order to access if the product (bank term deposit) would be ('yes') or not ('no') subscribed.

## Data Wrangling:

<B>1. Identify datatypes, count of null values, shape of data,etc <br>
   2. Handling Null values : Dealt with Null values, with maximum occurances of its related features. For example, if maximum of admins have completed university degree, then missing education value for admins will is filled with university degree only.<br>
   3. Dropped the rows for which maximum values of columns were null </B>
    
## Exploratory Data Analysis:

![Product subscribed with respect to Marital Status and Job](https://github.com/pranay-surana/Capstone_II/blob/master/figures/Capture1.PNG)

If we look from marital perspective, Married People have subscribed the product most. People who are admins have subscribed the product most.

![Product subscribed with respect to Education background and Month wise subscription](https://github.com/pranay-surana/Capstone_II/blob/master/figures/Capture2.PNG)

![Correlation Matrix of Features](https://github.com/pranay-surana/Capstone_II/blob/master/figures/Capture3.PNG)

Employee Variation rate, Euribor and Numbers of employee features are highly correlated. 

## Algorithms and Machine Learning

This problem is treated as classification problem, where we need to classify whether customer will subscribe to product or not (1 for yes and 0 for No)

In this case our governing case will be Recall score with balanced F1 score. As our values are not on same scale and  the target variable is skewed. Tried using different methods to deal with the imbalance and unscaled data:

    1.Initially checked with K-Means Algorithm to check how good is data to be classified into clusters and using Elbow method, identified  best count of cluster, the data could be clustered into.  
    2.Modelling on Unscaled Data : Before Scaling the data checked how models are performing on original dataset
    3.Modelling on Scaled and Imbalanced data: After Scaling the data, checked how models are performing with imbalanced and scaled dataset
    4.Balanced the Scaled Data: To balance the data, used different approaches as below :
    
        a.Class Weight: One of the simplest ways to address the class imbalance is to simply provide a weight for each class which h places more emphasis on the minority classes such that the end result is a classifier which can learn equally from all classes.
        b.Under Sampling – Near miss: The general idea behind near miss is to only the sample the points from the majority class necessary to distinguish between other classes.
        c.Over Sampling – SMOTE: Synthetic Minority Over-sampling Technique (SMOTE) is a technique that generates new observations by interpolating between observations in the original dataset.
     
     5.Reduced Features: After seeing scope of improvement in model performance after reducing features, tried to combine less important features in one, tried to club feature with continuous values.
     
Classification Algorithms used were: Logistic Regression, SVM, Ridge Classification, XG Boost, KNN and Random Forest. After evaluating best models after hyperparameter tunnig, the model with best combination for our recall and F1 score is SVM. We got recall score of 68 and F1 score of 44.

Features which are highly important to classify the customers are:

![Feature Importance](https://github.com/pranay-surana/Capstone_II/blob/master/figures/Capture4.PNG)
 
  
## Future Improvement

Different approach could be followed to fill missing values, Dataset could be label encoded and algorithms could be applied to calssify customers. 