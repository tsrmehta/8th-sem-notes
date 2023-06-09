
# Unit2
#unit2 

[Dimensionality Reduction](https://www.geeksforgeeks.org/dimensionality-reduction/)  
[Overfitting and Underfitting](https://www.geeksforgeeks.org/underfitting-and-overfitting-in-machine-learning/)  

> ***Row vector and column vector***
>
>   
> A row vector is a vector that has a single row. In dimensionality reduction, row vectors are often used to represent the features of a dataset.
>
> For example, consider a dataset that contains information about students, such as their age, gender, and GPA. The features of this dataset could be represented by the following row vectors:
>
> Code snippet
```
age = [18, 19, 20]
gender = ["male", "female", "male"]
GPA = [3.0, 3.5, 2.5]
```
>
> In dimensionality reduction techniques, such as Principal Component Analysis (PCA) or Linear Discriminant Analysis (LDA), row vectors and column vectors play different roles.
>
> A row vector is a vector that is oriented horizontally, meaning it is arranged as a single row of elements. In the context of dimensionality reduction, row vectors typically represent data points. Each element of the row vector corresponds to a feature or attribute of the data point. For example, if you have a dataset with three features (columns) and four data points (rows), each row vector would have three elements representing the values of the features for a particular data point.
>
> On the other hand, a column vector is a vector that is oriented vertically, meaning it is arranged as a single column of elements. In the context of dimensionality reduction, column vectors are used to represent eigenvectors or principal components. Eigenvectors or principal components are the directions in the data space along which the data exhibits the most variation. In PCA, for example, these eigenvectors are obtained by performing a linear transformation on the data matrix. Each column vector represents an eigenvector or principal component and has the same number of elements as the original features in the dataset.
>
>  During dimensionality reduction, row vectors (data points) are transformed by projecting them onto the eigenvectors or principal components represented by the column vectors. This projection allows for reducing the dimensionality of the data while preserving the most important information or variation in the dataset. The resulting transformed data will typically have a reduced number of dimensions, making it more manageable for analysis or visualization purposes.


>***how to represent a datasethow to represent a dataset***
>
>In machine learning, datasets are often represented as matrices, where each row of the matrix corresponds to a data point or sample, and each column represents a feature or attribute of the data. Here's a step-by-step guide on how to represent a dataset as a matrix:
>  
>  1. Identify the dataset: Determine the dataset you want to represent as a matrix. This could be a collection of samples or observations, where each sample has multiple features associated with it.
>  
>  2. Define the features: Identify the features or attributes of your dataset. These are the characteristics or variables that describe each data point. For example, if you have a dataset of houses, features could include the number of bedrooms, the square footage, the location, etc.
>  
>  3. Arrange the data: Organize the data in a tabular format, where each row represents a data point, and each column corresponds to a feature. Ensure that each data point is aligned with the appropriate feature values.
>  
>  4. Assign values to the matrix: Fill in the matrix with the values from your dataset. Each element of the matrix represents the value of a specific feature for a particular data point. Numeric features can be directly entered into the matrix, while categorical features may require some encoding, such as one-hot encoding, to convert them into numerical representations.
>  
>  5. Represent missing values: If your dataset contains missing values, decide how to handle them. Some common approaches include filling them with a specific value (e.g., mean, median) or using more advanced techniques like imputation.
>  
>  6. Check matrix dimensions: Ensure that the matrix dimensions are appropriate for your dataset. The number of rows corresponds to the number of data points, and the number of columns corresponds to the number of features.
>  
>  7. Normalize or standardize the data: Depending on the requirements of your machine learning algorithm, you may need to normalize or standardize the data in the matrix. This step ensures that all features are on a similar scale, preventing certain features from dominating the learning process.
>
>  Once you've completed these steps, you'll have a matrix representation of your dataset, which can be used as input for various machine learning algorithms. Remember that the specific details may vary depending on the programming language or library you're using for your machine learning tasks.


![[1_n3PLJaNvydTN8CCtY93qdg.webp]]

[Data preprocessing in Machine Learning](https://www.javatpoint.com/data-preprocessing-machine-learning)  
[Feature Normalization](https://www.javatpoint.com/normalization-in-machine-learning)  
> ***Mean of Data Matrix***
> 
> The mean of a data matrix is a measure of central tendency that represents the average value of each feature across all data points in the matrix. To calculate the mean of a data matrix, you perform the following steps:
>  
>  1. Given a data matrix with dimensions N x M, where N is the number of data points and M is the number of features, you want to calculate the mean for each feature.
>  
>  2. Compute the mean for each feature separately. For a particular feature, sum up the values of that feature across all data points and then divide by the total number of data points.
>  
>  3. Repeat this process for each feature in the data matrix, resulting in a vector of mean values with length M.
>  
>  Mathematically, the mean of a data matrix X is calculated as follows:
>  
>  For each feature i from 1 to M:
>  - Compute the sum of the i-th feature: sum_i = Σ X_ji, where j ranges from 1 to N (data points).
>  - Calculate the mean of the i-th feature: mean_i = sum_i / N.
>
> The resulting vector mean = [mean_1, mean_2, ..., mean_M] represents the mean values for each feature in the data matrix.
>
>  It's worth noting that when calculating the mean, ensure that the data matrix is properly formatted, missing values are handled appropriately (e.g., excluding them from the calculation or imputing them), and any necessary preprocessing steps (e.g., normalization or standardization) have been applied.


[Column standardization](https://medium.com/@jalesh.j/column-normalization-and-column-standardization-in-machine-learning-e056501056b)  
[Covariance of matrix](https://www.geeksforgeeks.org/covariance-matrix/)  
[PCA Theory](https://www.geeksforgeeks.org/ml-principal-component-analysispca/)  
[PCA Numerical](https://www.youtube.com/watch?v=v5vEP9HgdZM)  
[PCA Numerical](https://youtu.be/MLaJbA82nzk)  
[Mam Notes Source 1](https://dugamakash.medium.com/dimensionality-reduction-zero-to-hero-part-i-2a821ad80099)  
[Mam Notes Source 2](https://dugamakash.medium.com/dimensionality-reduction-zero-to-hero-part-ii-747bb1ff4012)  


# Unit3
#unit3 

[Supervised Learning: Definition, how it works](https://www.javatpoint.com/supervised-machine-learning)  
[KNN](https://www.javatpoint.com/k-nearest-neighbor-algorithm-for-machine-learning)  
[Naive Bayes](https://www.javatpoint.com/machine-learning-naive-bayes-classifier)  
[Descision Tree](https://www.javatpoint.com/machine-learning-decision-tree-classification-algorithm)  
[Linear Regression](https://www.javatpoint.com/linear-regression-in-machine-learning)  
[Logistic Regression](https://www.javatpoint.com/logistic-regression-in-machine-learning)  
[SVM](https://www.javatpoint.com/machine-learning-support-vector-machine-algorithm)  
[Regression vs classification](https://www.javatpoint.com/regression-vs-classification-in-machine-learning)  
[Linear vs logistic](https://www.javatpoint.com/linear-regression-vs-logistic-regression-in-machine-learning)  

# Unit4
#unit4

[Unsupervised Learning](https://www.javatpoint.com/unsupervised-machine-learning)  
[K-mean](https://www.javatpoint.com/k-means-clustering-algorithm-in-machine-learning)  
// Ensemble Classifier:- Mam Notes  
[Boosting](https://www.javatpoint.com/what-is-boosting-in-data-mining)  
[AdaBoost](https://www.analyticsvidhya.com/blog/2021/09/adaboost-algorithm-a-complete-guide-for-beginners/)  
[Bagging](https://www.simplilearn.com/tutorials/machine-learning-tutorial/bagging-in-machine-learning)  
[Random Forest](https://www.javatpoint.com/machine-learning-random-forest-algorithm)  
[Confusion Matric](https://www.javatpoint.com/confusion-matrix-in-machine-learning)  
[Auc-Roc](https://www.analyticsvidhya.com/blog/2019/08/11-important-model-evaluation-error-metrics/#Types_of_Predictive_Models)  
[Mean Absolute devision](https://www.geeksforgeeks.org/mean-absolute-deviation/)  

> ***Distribution of errors***
> 
> In machine learning, the distribution of errors refers to the pattern or characteristics of the errors made by a predictive model when compared to the true values or labels of the data. Understanding the distribution of errors is important for evaluating and improving the performance of machine learning models.
>  
>  Here are a few common types of error distributions in machine learning:
>  
>  1. Random Errors: Random errors occur when the model's predictions deviate from the true values in an unpredictable manner. These errors are typically caused by noise in the data or inherent randomness in the underlying process being modeled.
>  
>  2. Systematic Errors: Systematic errors, also known as bias, arise when the model consistently predicts values that are either higher or lower than the true values. These errors can occur due to flaws in the model's assumptions or limitations in the training data.
>  
>  3. Skewed Errors: Skewed errors occur when the model consistently overestimates or underestimates the true values in a particular range or direction. Skewed errors may indicate a problem with the model's calibration or an inherent bias in the training data.
>  
>  4. Heteroscedastic Errors: Heteroscedastic errors refer to a situation where the variability of the errors is not constant across the range of predicted values. In other words, the spread of errors varies based on the predicted values. This can indicate that the model's performance is influenced by specific factors or conditions.
>  
>  5. Outliers: Outliers are data points that significantly deviate from the expected pattern or distribution. Outliers can introduce substantial errors and may require special handling during model training or evaluation.
>  
>  Understanding the distribution of errors can help identify potential issues with a machine learning model and guide improvements. Techniques such as error analysis, visualizations, and diagnostic metrics (e.g., mean squared error, mean absolute error) can provide insights into the nature and magnitude of the errors.







