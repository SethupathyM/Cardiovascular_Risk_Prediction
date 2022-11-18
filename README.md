# Cardiovascular_Risk_Prediction

Built Supervised Binary classification model to help patients to take precautions and change lifestyle by risk prediction of cardiovascular disease in upcoming 10 years.

# Problem Statement

The dataset is from an ongoing cardiovascular study on residents of the town of Framingham, Massachusetts. The classification goal is to predict whether the patient has a 10-year risk of future coronary heart disease (CHD). The dataset provides the patients’ information. It includes over 4,000 records and 15 attributes.Each attribute is a potential risk factor. There are both demographic, behavioral, and medical risk
factors.

# Attributes

• Sex: male or female("M" or "F")

• Age: Age of the patient;(Continuous - Although the recorded ages have been truncated to whole numbers, the concept of age is continuous) Behavioral

• is_smoking: whether or not the patient is a current smoker ("YES" or "NO")

• Cigs Per Day: the number of cigarettes that the person smoked on average in one day.(can be considered continuous as one can have any number of cigarettes, even half a cigarette.)

• BP Meds: whether or not the patient was on blood pressure medication (Nominal)

• Prevalent Stroke: whether or not the patient had previously had a stroke (Nominal)

• Prevalent Hyp: whether or not the patient was hypertensive (Nominal)

• Diabetes: whether or not the patient had diabetes (Nominal)

• Tot Chol: total cholesterol level (Continuous)

• Sys BP: systolic blood pressure (Continuous)

• Dia BP: diastolic blood pressure (Continuous)

• BMI: Body Mass Index (Continuous)

• Heart Rate: heart rate (Continuous - In medical research, variables such as heart rate though in fact discrete, yet are considered continuous because of large number of possible values.)

• Glucose: glucose level (Continuous)

• 10-year risk of coronary heart disease CHD(binary: “1”, means “Yes”, “0” means “No”) - Dependent Variable

# Handling Imbalanced Dataset

The given data is highly imbalanced data so I have used SMOTE Technique to overcome this problem. SMOTE is the technique of handling imbalanced dataset by creating synthetic datapoints of minority class. Here class 1 is the minority class which is oversampled by SMOTE by synthetic datapoints.

Dependent Variable count (Before SMOTE)

![image](https://user-images.githubusercontent.com/102578847/202611312-736a0288-ae92-44bd-bf25-b13b5d4115ce.png)

Dependent Variable count (After Sampling)

![image](https://user-images.githubusercontent.com/102578847/202613556-951ee9c9-f0ea-4dcf-b323-23a44d8b68fd.png)

# Model Implementaion and Metrics

ROC Curve would be meaningless for Imbalanced dataset.

ROC Curve --> True_positive_rate vs False_positive_rate

True_positive_rate = True_positive/(True_positive + False_negative)

False_positive_rate = False_positive/(False_positive + True_negative)

For an Imbalanced dataset True_negative would be always high, if the majority class is 0. So we always get less False_positive_rate.

Presicion Recall curves would be appropriate for Imbalanced dataset.

#Evaluation

| Model Name  | MSE  | Train R2 score | Test R2 score | Adjusted R2 score
| :------------: |:---------------:| :-----:| :-----:| :-----:|
|Linear Regression | 133073 | 0.66 | 0.65 | 0.64 |
|Polynomial Regression | 70534 | 0.84 | 0.82 | 0.82
|Random Forest Regressor | 20.37 | 0.90 | 0.87 | 0.86|
|Gradient Boost Regressor | 24.19 | 0.86 | 0.84 | 0.84|

# Conclusion

Achieved ROC-AUC score of 0.978 and used confusion matrix to visualize TP,TN,FP,FN. ln focus to reduce False Negatives model is designed.

