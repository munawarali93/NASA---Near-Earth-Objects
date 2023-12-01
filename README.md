# NASA-Near-Earth-Objects
ERDOS Data Science BootcampNASA - Near Earth Objects 

Team Members: 

Munawar Ali, Cagatay Ayhan, Ece Karacam, Mostofa Hisham, Waleed Ahmed

Mentor: Kashif bari  

# Dataset 

We used NASA's dataset on near earth objects available here:
https://www.kaggle.com/datasets/sameepvani/nasa-nearest-earth-objects/data

Dataset has 90836 observations with 9 features.

## Preprocessing

All the data was first checked to ensure no null values were present and it was clean. New features were created such as average diameter. One-hot encoding was also performed to replace the boolean values in the target variable to 0's and 1's. Standard Scaling was finally applied to the dataset before training.  

# Models

We attempt a number of models to try to predict the near earth objects. These are summarized below: 

Random Forest: This model is an ensemble learning method which relies on bagging: trees are fit independently, and results are averaged for all models. Model parameters used were n_estimators = 50, max_depth = 4. This gave a very good result with an F1-score of 95%.   

Decision Trees: Decision trees with varying maximum depths have been trained. We implement the algorithm up to 20 layers, beyond which would have overfitted the data. Nonetheless, predictions using decision trees are not entirely accurate due to the skewed nature of the data in favor of the non-hazardous materials. More specifically, they exhibit an average accuracy of 90%, their F1 score is only 38%. In conclusion, these trees do not perform well in detecting hazardous objects. 

Logistic Regression: Logistic regression for binary classification was trained. As logistic regression assumes independence of features so features depending upon each other were removed. The model gave better results i.e., F1 score for the train and test set was 95 and 94 respectively.  

XGBoost: XGBoost is a versatile algorithm for binary and multiclass classification. It uses an ensemble of decision trees to model the relationship between features and the target variable. It employs logistic function for binary classification. Sigmoid transformation ensures predictions between 0 and 1. After doing some careful selection of hyperparameters we get better results here as compared to other models we trained. F1 score for the train and test set was 96 and 95 respectively. 

