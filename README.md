# Breast Cancer Wisconsin Diagnostic
> Breast cancer, one of the most malignant types of cancers, has been seriously threatening both the physical and mental health of women in the world. However, this is curable if detected in an early-stage as a non-metastatic disease thus underlying the importance of early detection and need to conduct research in these lines. The Breast Cancer Wisconsin (Diagnostic) Dataset gives an opportunity to apply Machine learning techniques in such a research process. An important step before deploying any Machine Learning algorithm is to study the characteristics of the given dataset, commonly called Exploratory Data Analysis (EDA).

![image](https://user-images.githubusercontent.com/98254584/211904525-4d90a133-c1c5-4006-8f05-5182e871a179.png)

## Introduction:
> Diagnosis of breast cancer is traditionally done by a full biopsy which is an invasive surgical method. A less invasive method called Fine Needle Biopsy (FNB), allows for examination of a small amount of tissue from the tumor.

> This dataset was obtained by analyzing the cell nuclei characteristics of 569 images obtained by Fine Needle Aspiration of the breast mass. Each of the images are classified(diagnosed) as being “Benign” or “Malignant”.

> Structural Analysis: Before we look into the content of the data, we first need to look into the general structure of the data , i.e., the number of rows (data points)and number of columns (features) in it.

## Data Preprocessing
> The column “diagnosis” has two values: **Malignant** and **Benign**. Machine learning models can be built on data that is made of just numbers. Hence, I have replaced Malignant with number 1 and Benign with number 0. Any two numbers can be used but 0 and 1 are the most commonly used for classification purposes.

![breast cancer](https://user-images.githubusercontent.com/98254584/211903295-28cbfc00-3f08-4959-9c9e-c9db19583f42.jpg)

**To prepare our data for machine learning, two steps are required**:

1. Divide data into X (features) and y (target)
X refers to all the variables used by the machine model to make a prediction. The characteristics correspond to the names of the columns. Y, on the other hand, refers to a target variable or the correct answer. In our case, the correct answer (what we want the machine to predict) is whether the CT scan shows a benign (1) or malignant (0) tumor.

2. Divide data into test and training sets
Essentially we train the model on the train (about 80% of the data) and then see how well it can predict the target variable on the remaining 20% of the data. To split the data, we use a scikit-learn train_test_split module.

>   I've split the data into two Parts Based on Diagnosis to find out that there are almost perfect linear patterns between the radius, perimeter, and area attributes that are hinting at the presence of multicollinearity between these variables. Another set of variables that possibly imply multicollinearity are the concavity, concave_points, and compactness.

## Supervised Learning
As our system learns under the supervision of a teacher, the model has both a known input and output used for training. The teacher knows the output during the training process and trains the model to reduce the error in prediction. The two major types of supervised learning methods are Classification and Regression.
## Examples:
1. *K-Nearest Neighbors (KNN)* is an algorithm that assumes that similar things exist nearby. "Birds of a feather flock together." The KNN algorithm calculates the distance between different data points and groups them based on their proximity or distance. "K" in KNN is a parameter that refers to the number of closest neighbors to be included in the voting process. For example, we are introducing a new data point. "Is this scan benign or malignant?" If k=5, the answer depends on the answers of 5 neighbors. If 4 out of 5 neighbors are malicious, the new data point is also classified as malicious. We can find the best number K by experimentation, running the algorithm multiple times and choosing the K that has the least error.
> Advantages:
> 
>> Simple and easy to implement.
>> 
>>Can be used for classification, regression and search problems.
>>
>Disadvantages:
>
>>Slows down as the number of previews and / or functions increases.

2. *Linear SVC_Vector Machines (SVM)* is an algorithm used for classification, regression, and outlier detection models. An SVM model tries to find the optimal hyperplane (threshold) between different classes. The closest point to the hyperplane is called the support vector point. The distance between the support vector points and the hyperplane is called the margin. The further the points of the support vector are from the hyperplane, the higher the probability that they are correctly classified. LinearSVC (Support Vector Classification) is a class of SVM, used for classification problems, and uses a linear kernel (sometimes referred to as "non-kernel"). In other words, classes can be separated with a single line.
> Advantages:
> 
>> Effective when the number of features are more than training examples.
>> 
>> Best algorithm when the classes are separable.
>> 
>> Suited for extreme case binary classification.
>> 
> Disadvantages:
> 
>> Not suitable for large datasets, because takes a long time to process.
>> 
>> Does not perform well with overlapping classes.
>> 
>> Selecting the appropriate kernel function can be tricky.


