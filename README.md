# Pima Indian Diabetes Prediction Analysis and Summary  
  
## Dataset:
Dataset for this analysis is taken from Kaggle which is a subset of larger database consisrrting only of female patients at least 21 years old of Pima Indian heritage (originally from the National Institute of Diabetes and Digestive and Kidney Diseases):
https://www.kaggle.com/uciml/pima-indians-diabetes-database  

The datasets consists of several medical predictor variables and one target variable, **Outcome**. Predictor variables includes the number of pregnancies the patient has had, their BMI, insulin level, age, and so on.

## Method for analysis and prediction model:
The dataset is fairly balanced for this binary classification problem i.e. diabetes and non-diabetes sample size are comparable.  
Input features are centered to their mean and scaled by their standard deviation before model exploration.  
Among the models tried using scikit-learn, Linear SVM and Logistic Regression performed better in cross validation while tree based methods, Decision Tree and Random Forrest are worse with wider distribution of their acccuracies in test dataset. Finally ensamble method was applied with 3 classifiers combined on the test to get the final model: Linear SVM, radial SVM and Logistic Regression.  
ROC curves and precision vs. recall were explored for all the models on test dataset.  
A neural network model with 5 fully connected layers was explored using Keras for prediction model with loss: binary_crossentropy, Optimizer: Adam, batch size: 50 and epoch: 150 (more is better but we have a small dataset here), activation was relu except the output layer being with sigmoid activation.  

## Key findings:
* Close to 80% overall test accuracy was obtained based on this dataset to predict diabetes in a person using ensemble model among different methods evalauted as well as NN model.
* Non diabetes cases were predicted more accurately than diabetes cases.
* NN model gave better prediction of diabetes cases than ensamble model (66% vs. 54%).
* Based on Random Forest feature importance, Glucose, BMI, Age and diabetes pedigree are top causes for diabetes.
* Based on parameter distribution and correlation, no single parameter can predict diabetes.
## Future work and improvement
* More data. This dataset is a small sample size including only women moer than 21 years old. 
* Feature engineering. Need to see impact of any cross term or higher order term.
* Larger NN model. Typically larger networks with more layers and more iterations (epochs) improve diabetes prediction accuracy.
