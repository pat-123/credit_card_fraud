This project is about predicting the no of defaulters who will not pay the credit card bill next month

Few points worth mentioning regarding directory structure:
- csv is placed under data/raw/
- Processed csv is places under data/processed after computation
- Notebook is present in notebooks folder
- credit_card_fraud is a package which load all initial packages(__init__.py) and sets data file paths under config.py
  ++ Abstracts the messy paths in the main notebook to here, so that cleaner view can be provided
- scripts folder is a placeholder for future purposes
- How to run this?
  ++ start Anaconda prompt and go to this folder's parent location and type jupyter notebook
  ++ notebook starts with the parent folder as the base location and you can navigate to different projects from there


I have used RandomForestClasssifier, naive bayes, Logistic regression and plotted auc curve to measure accuracy of the models
++Use KFolds instead of train_test_splits 

---------------------------------------------------
Future updates
--------------------------------------------------
Integrate auc curve in to sklearnerhelper class framework along with existing framework for differnt model creation

-------------------------------------------------- 
RESULT
--------------------------------------------------
SVM literally hangs since the no of observation is >40k, Time complexity being O(n^2 * no of features)..So not useful here

Naive Bayes
	Model accuracy - 0.55
	auc = 0.72
	**Accuracy in Identifying defaulters 74.37437437437437
	**Wrongly telling a person will not default, whereas he is going to be 25.625625625625624

RandomForest
	Model accuracy - 0.72
	auc = 0.79
	**Accuracy in Identifying defaulters 67.33784746970777
	**Wrongly telling a person will not default, whereas he is going to be 32.66215253029223

Logistic Regression
	Model accuracy - 0.66
	auc = 0.74
	**Accuracy in Identifying defaulters 61.60506160506161
	**Wrongly telling a person will not default, whereas he is going to be 38.39493839493839

All the results are calculated with kfolds = 5

Auc score is best for randomforest, but recall and fnr is best for Naive Bayes

