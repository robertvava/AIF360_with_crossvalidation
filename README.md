# AIF360_with_crossvalidation

### AIF360

The AIF360 Library is an IBM open-source project, providing datasets and several pre, in, and post processing methods.  
One dataset was been chosen for the current analysis: Adult Income Dataset.
  
#### Adult Dataset 

   The Adult Census Income Dataset has been extracted from the 1994 Census bureau database. There are 7 numerical and 11 categorical features in the original dataset. 
  For this analysis, the features have been pre-processed to contain 17 binary categorical features out of which 4 are effectively unique: race, sex, age (decades) and education (years), using a predefined function available from AIF360. 
  The protected attribute investigated in this analysis is ‘sex : female’ There are 48842 datapoints in total.  
  
  The AIF360 library provides a handy function which transforms non-binary variables and combines multiple categories into one-hot encoded variables. There are specially defined functions for both Adult and German Datasets. 
  Additional pre-processing has been effectuated on both datasets, using the MinMax scaler. This scaler transforms each feature x to a given range. The formula for this scaler is: 
  
  
  An important feature of a successful machine learning model is the ability to generalize to novel data. The risk of overfitting is high when the model is being trained on the same sample data. 
  Thus, it can start to emulate the noise present in the data that it has been trained on.	the noise present in the data that it has been trained on. In order to mitigate this risk, a method called K-fold cross-validation can be utilized. 
  In this method, the training data is split into K folds (sub-groups), each FoldK playing the role of the test data, on turn, while the rest of the folds are aggregated as the training data, and utilized for training the model. 
  The metrics of interest, such as accuracy or fairness criteria are computed for each iteration, and averaged at the end. This is a powerful method which can confirm the validity of the results. 
  
  The models were selected based on three factors: Best for fairness, best for accuracy, and best overall (based on the custom-made criterion). In total, 12 models were selected and analysed, 6 for each. They are outlined as follows: 'Standard_Fair', 'Standard_Accurate': 'Standard_Best', 'RW_Fair’ , 'RW_Accurate' , 'RW_Best' for each dataset. RW is shorthand for reweighted.
  
Based, on the trends highlighted in graphs 1, 2, and 3, it becomes evident that, generally, a better accuracy leads to lower fairness outcomes. However, when Reweighting is applied, EoP is significantly improved (between one and two standard deviations).  
And interesting observation is related to the effects of the classifier on accuracy and fairness. It is shown that SVC has more varied outcomes, and as will be shown in Figure X, it is also generally preferred over Logistic Regression. As well, hyperparameters play an important role in the final outcomes.

