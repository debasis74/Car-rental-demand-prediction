

-------------------------------------------------Demand of the Car Rentals on hourly basis---------------------------------

About the data set:
 The data set is of a car rental company based out of Bangalore.In recent times, the demand for cars is on the rise. As a result, the company would like to tackle the problem of supply and demand. The ultimate goal of the company is to strike the balance between the supply and demand inorder to meet the user expectations. 

Our objective:
The main objective of the problem is to develop the machine learning approach to forecast the demand of car rentals on an hourly basis.

Approach Followed:
The data was mostly dependent on time related features. At first I sorted the data by combining 
Date and hour, as some cases were there where hour 9 was after hour 23 in a particular day. So, this was sorted at first. Than the basic pipeline of machine learning was followed.  

Data Preprocessing
As the data had mostly time related columns, At the preprocessing step every possible features from the date column like day_of_week,month, week_of_year etc. Were made.
The data was divided into 3 parts, train , valid1, valid2. 
EDA was done on the train set on the date related features(like day_of_week,quarter)that were engineered in the preprocessing step.The inferences from each analysis was used in future feature engineering steps.

Feature Engineering:
In this step,mostly two features were grouped and a new feature was formed. The encoding method that was followed was mean encoding.
Idea behind this was: After doing EDA, an inference was found out that day of week and hour mostly had an impact on demand. Therefore, combining them might give better results.(This was followed for other date related features also.)
As this is a time dependent data past recent values will have a larger impact on current value. So, I tried lag features and rolling mean but was not able to replicate them in test set, so had to use only date related features.
The Feature selection methods were: Pearson’s correlation selectKbest and also based on intution.

So, the final model that was used was lightgbm as it had better rmse score in valid1 set. I reached it by following the steps that I have mentioned above.




   
