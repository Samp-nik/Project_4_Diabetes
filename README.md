#### Project_4_Diabetes

# Context
  Diabetes impacts millions of Americans each year and causes a significant financial burden on the economy. Diabetes is a chronic disease in which individuals lose the ability to effectively regulate levels of glucose in the blood, and can lead to reduced quality of life and life expectancy. Insulin from the pancreas helps enable cells within the body to use those sugars in th bloodstream for energy. When an individual has diabetes, the body is either not making enough insulin or is unable to effectively use the insulin.
Although there is no cure for diabetes, strategies like losing weight, eating healthy, being active, and receiving medical treatments can mitigate the harms of the disease. 

# Data 
The Behavioral Risk Factor Surveillance System (BRFSS) is a health-related telephone survey that is collected annually by the *CDC*. The survey collects responses from over *400,000 Americans* on health-related risk behaviors, chronic health conditions, and the use of preventative services. 
The data package provided 3 files. For this project, the csv file we focused on is the one titled *diabetes_binary_5050split_health_indicators_BRFSS2015.csv*. 
This csv file has 70,693 survey responses to the CDC's survey. This is an equal split of respondents with no diabetes and either pre-diabetes or diabetes. The target variable *diabetes_binary* has 2 classes, 0 for no diabetes and 1 for diabetes/pre-diabetes.


# Supervised Learning 
This code performs binary classification on health indicator data related to diabetes. Initially, it reads the data from a CSV file into a Pandas DataFramee. It then creates separate sets for labels (y) and features (X), with the labels indicating the presence or absence of diabetes. The features include various health indicators like BMI, smoking status, and age. After checking the balance of the labels, the data is split into training and testing sets. A logistic regression model is then fitted using the original data, and its performance is evaluated using metrics such as accuracy, a confusion matrix, and a classification report. The process is repeated with resampled training data using the RandomOverSampler to address class imbalance, and the resulting model is also evaluated. The balanced accuracy scores and classification reports for both models are provided. The logistic regression model achieves an accuracy of 75% on the original data and 74% on the resampled data, indicating a balanced performance for the binary classification task. A warning is raised in the resampled model, suggesting potential future improvements in model training convergence.

# Neural Network and Model Optimizer
Setting up the dataset in the same way as the Supervised Learning, My initial code had a very low accuracy rate, it improved when I moved it up to three layers, with 64 nodes on the first, 32 on the next and 16 on the next and 1 on the last. Using the activation "Softmax" moved my accuracy above 75%. I then built the model optimizer, which after going through many permutations gave a network build of 5 layers consisting of 9 nodes, followed by 1, followed by 3,follwed by 9,and finished with 1. This model used the "relu" activation and was pretty close to achieveing a 76% accuracy rate. I believe if less binary data was collected, and more with value variety, the model could definitely increase its accuracy. While far too inaccurate for the medical field it could still be used as a risk indicator that could help push people to visit their doctor. Just have to put a disclaimer on it in 4pt font, "For Entertainment purposes only"

# Visualizations
We created key visualizations to show the risk factors  of Diabetes. 
![liz graph](https://github.com/Samp-nik/Project_4_Diabetes/assets/136443525/b886aa19-ebb4-4222-a9cc-c7061a382dc1)

#### BMI Visuals
![BMI Visuals](https://github.com/Samp-nik/Project_4_Diabetes/assets/136443525/842983e9-bed3-4871-a660-8bc9b5d4704e)

# Conclusion
  The model was able to successully create a model that reflected 75% accuracy for prediciting diabetes based on certain risk factors. The original dataset provided a higher accuracy of over 80%, however, the dataset had a greater split of those who actually has diabetes. This showed potential inaccuracies in the model's prediction of diabetes. The 5050 binary split dataset provided an accuracy of 70%. Through filtering of the data, we were able to successfully raise the accuracy to 75%. 
