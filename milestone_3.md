# Milestone 3
## Preprocessing:
  Main parts of preprocessing we added was we imputed and replaced a couple more of our features that had no value into 'None', which meant that things didn't have any special conditions. We did one hot encoding for most of our categorical values. We used a Naive Bayes model to try to predict the Accident Severity of a crash. Our grounds truths and predictions are 3 for a minor accident, 2 for a serious accident, and 1 for a fatal accident.
	Naive Bayes Training Report <br>
	<img width="430" height="192" alt="image" src="https://github.com/user-attachments/assets/4903b2e5-6f63-4702-bc70-6b037855e032" />
	<br>
	Naive Testing Report <br>
	<img width="434" height="137" alt="image" src="https://github.com/user-attachments/assets/8939a515-acd5-4749-9946-0d538196b4e7" />
	<br>

# First Model Training:
  When it comes down to accuracy both training and testing models came out to be around 65%. This is also the case for Precision, Recall, and F1 score for each accident severity class. In addition, both models also agree that the scores for class 1 and 2 are both significantly lower than class. This could be due to the fact that we have a lot more samples that have a class 3 accident severity. This also means we are experiencing a lot more false positives for class 1 and 2 and missing a lot of true positives. 
## Fitting Graph Evaulation:
  Our model lies on the left end of the fitting curve, based on how low our train and test accuracy were underfitting our model. Increasing our learning rate results in a slightly better fit as represented by the var_smotting vs accuracy graph, so our best model is the one with the var smoothing of 1e-6. The next model we were thinking of is a KNN because upon initial testing with a KNN provided better accuracy report, the only downside is that it takes a very long time to run, even on SDSC.

<img width="1109" height="660" alt="image" src="https://github.com/user-attachments/assets/fcacf9ac-e79d-4c61-b46c-e4ac05461ca2" />
<img width="1092" height="679" alt="image" src="https://github.com/user-attachments/assets/1be80902-a884-43ca-b1df-f843708c8ecc" />

## Conclusion:
  Our Naive Bayes has an accuracy of around 65% which means it does better than guessing what the accident severity is. Some ways that we can improve it is by conducting hyperparameter tuning specifically on our alpha and var_smoothing.  We can also drop more features. Another way that we can improve is by building our own Naive Bayes model from scratch that uses both numerical and categorical data as we realized that there isn't a Naive Bayes model in Scikit Learn that cause handle both. Analyzing our classification report, we see that we are getting the good accuracy for accident severity 3, but low and very low accuracies for accident severity 2 and 1. Taking a look at our data, around 85% of our data was accident severity 3 which could be a cause of the low accuracies for accident severity 2 and 1. This means we could improve it by using SMOTE or ADASYN oversampling to get more data for accident severity 2 and 1 and improve its accuracy and the accuracy of the whole model.
## Code:
[Milestone 3](milestone_3.ipynb)
