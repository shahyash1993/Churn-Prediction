*************************************************************************
*				PROJECT REPORT				*
*-----------------------------------------------------------------------*
*									*						
*	Churn Prediction of Telecommunication Company			*
*									*				
*-----------------------------------------------------------------------*
*									*				
*	Red ID	:	820859111 		|	820872254	*	
*	Name	:  	Yash P Shah		|	Tanay Jani	*		
*									*				
*************************************************************************


--------
Abstract
--------
Churn prediction minimizes customer defection by predicting which customers are likely to cancel a subscription to a service. This has become a common trend across every businesses. The data extracted from telecom industry can help analyze the reasons of customer churn and use the information to retain the customers.


--------
Our Work
--------
The project mainly focuses on "Churn prediction" based on the 20 features given in the dataset. We have used five different classification algorithms of Machine Learning Technology, i.e., RANDOM FOREST, LOGISTIC REGRESSION, DECISION TREES, NAIVE BAYES, and GRADIENT BOOSTED TREES to predict the churn accuracy. For every model, along with the accuracy of all features, accuracy of every single feature is also calculated and the best accuracy amongst all the features is recorded. At the end, all the models are compared with their best accuracy, best feature, and the execution time. In conclusion, we have found the "DECISION TREES" to be the best suited algorithm amongst all with the highest accuracy of "87.54325259515571%" and reasonable execution time of "63 seconds".


--------------
Running in AWS
--------------
1)Package the code using sbt.Use the command sbt package in project directory.
2)Creating an Manifest.mf file. 
3)Create Amazon S3 bucket for the datafile and jarfile.
4)Create an EMR cluster and in the spark-submit option enter --class churn_prediction_gradient_boosted_classification.
5)Setting the to fetch jarfile from s3 to EMR cluster.
6)Will take a couple of minutes to start the cluster.


---------------------------------------
Running the .dbc notebook in databricks
---------------------------------------
1) Find the attached .dbc file in the project folder
2) Import the .dbc file into DataBricks
	//A simple community account on DataBricks would also work.
3) To add the attached dataset "churn.csv", Go to DataBricks dashboard, Click on "Data", select "default" as database, 
	and when the new "Tables" aside menu pops up, click on the "+" sign and simply drag the "churn.csv" to the shadded area.
4) In the menu bar, Click on the "Attached:cluster" and Start it
5) Press "Run all"


-----------
DataSet URL
-----------
http://www.dataminingconsultant.com/data/churn.txt


--------------
DataSet Schema
--------------

root
 |-- state: string (nullable = true)
 |-- account_length: double (nullable = true)
 |-- area_code: string (nullable = true)
 |-- phone: string (nullable = true)
 |-- intl_plan: string (nullable = true)
 |-- vMail_plan: string (nullable = true)
 |-- vMail_messages: double (nullable = true)
 |-- day_mins: double (nullable = true)
 |-- day_calls: double (nullable = true)
 |-- day_charge: double (nullable = true)
 |-- eve_mins: double (nullable = true)
 |-- eve_calls: double (nullable = true)
 |-- eve_charge: double (nullable = true)
 |-- night_mins: double (nullable = true)
 |-- night_calls: double (nullable = true)
 |-- night_charge: double (nullable = true)
 |-- intl_mins: double (nullable = true)
 |-- intl_calls: double (nullable = true)
 |-- intl_charge: double (nullable = true)
 |-- custServ_calls: double (nullable = true)
 |-- churned: string (nullable = true)

 
-------
Results
-------
 
Model			 		| Best Accuracy 	| Feature 			| Run Time
----------------------------------------|-----------------------|-------------------------------|----------
RANDOM FOREST 				| 0.8547774832689106 	| day_charge   			| 80 sec
LOGISTIC REGRESSION 			| 0.7940277142518337 	| state        			| 44 sec
DECISION TREES 				| 0.8754325259515571 	| vMail_messages 		| 63 sec
NAIVE BAYES 				| 0.8716452742123687 	| phone 			| 50 sec
GRADIENT BOOSTED TREES  		| 0.8640873015873016 	| state 			| 218 sec
