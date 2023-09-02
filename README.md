# Breast-cancer-classification
## Logistic Regression
Logistic Regression is a widely used classification algorithm for several reasons:

1. **Simplicity**: Logistic Regression is a simple yet effective algorithm for binary and multiclass classification. It's easy to understand, implement, and interpret, making it a great choice, especially when you want a straightforward solution.

2. **Getting to know the independent variables** The coefficients in a logistic regression model represent the strength and direction of the relationships between input features and the target variable. This interpretability is valuable when you need to understand the impact of different features on the classification outcome.
 It automatically assigns lower coefficients to less informative features.

3. **Efficiency**: Logistic Regression is computationally efficient and can handle large datasets with relatively low memory and processing power requirements.
4.  Training a Logistic Regression model is typically faster than more complex algorithms like Random Forest or Gradient Boosting. 

5. **Probabilistic Interpretation**: Logistic Regression provides probabilistic predictions. It estimates the probability of an input belonging to a particular class. This can be useful when you want not only the class label but also the confidence level associated with the prediction.

6. **Regularization**: Logistic Regression can be regularized to prevent overfitting. L1 (Lasso) and L2 (Ridge) regularization techniques can be applied to control the complexity of the model and improve its generalization performance.

7. **Binary and Multiclass Classification**: While initially designed for binary classification (two classes), Logistic Regression can be extended to handle multiclass classification problems using techniques like one-vs-rest (OvR) or softmax regression.

8. **Well-suited for Linearly Separable Data**: When the classes in the dataset can be effectively separated by a linear decision boundary, Logistic Regression tends to perform well. However, it can also be used with nonlinear data by incorporating feature engineering or polynomial features.

9. **Baseline Model**: Logistic Regression often serves as a baseline model. It provides a benchmark against which you can compare the performance of more complex models. If Logistic Regression achieves satisfactory results, there may be no need for a more complex model.


Logistic Regression Dis-advantages,
It's essential to note that it may not perform as well as more complex models in cases ,
where the relationship between features and the target variable is highly nonlinear or when there are complex interactions between features.
In such cases, more advanced algorithms like Random Forest, Support Vector Machines, or Neural Networks may be considered.
However, Logistic Regression remains a valuable tool in the machine learning toolbox for many classification tasks.


## cross_val_score

Here's what happens step by step when you call cross_val_score:

cross_val_score internally splits your dataset X and y into five (as specified by cv=5) different training and validation sets.

For each fold, it trains the **LogisticRegression** model (specified by the model variable) on the training set,** which consists of 80% of the data in each fold**.

After training, it evaluates the model's performance by making predictions on the validation set (the remaining 20% of data in each fold) and computes the accuracy for that fold.

This process is repeated for all five folds, resulting in an array of five accuracy scores (one for each fold).

Finally, cross_val_score returns these accuracy scores, which you can then use to calculate statistics like the mean and standard deviation of the accuracy scores, as shown in the original example.

### Output = 
cross_val_score returns an array of accuracy scores,
one for each fold of the cross-validation.
In my case, accuracies is an array containing these accuracy scores.

'''I obtained the % Mean of result accuracy and % of Std deviation of result'''

**1. The higher the mean of result the better . I got 97%**

**2. The lower the std of result the better . I got 1.15%**

The standard deviation (std) of accuracy scores in cross-validation indicates how much the accuracy scores vary across different folds. In your case, a standard deviation of 1.97% means that the accuracy scores across the five folds had an average variation of approximately 1.97% from the mean accuracy score.

Whether **a standard deviation of 1.97% i**s considered good or bad depends on the specific problem and dataset you are working with. Here are some guidelines to help you interpret the standard deviation of accuracy:

Low Standard Deviation: A low standard deviation (close to 0%) suggests that the model's performance is consistent across different subsets of the data. This is generally desirable because it indicates that the model is not overly sensitive to the particular way the data is divided.

Moderate Standard Deviation: A moderate standard deviation (between 1% and 5%, for example) may be acceptable, especially for larger datasets. It indicates some variability in performance but not to an alarming degree. It's important to consider the context and requirements of your application.

High Standard Deviation: A high standard deviation (greater than 5%) suggests that the model's performance is highly variable across different folds. This could be a sign of overfitting, data leakage, or that the model is not stable. It may require further investigation and model tuning.

In your case, a standard deviation of 1.97% is generally reasonable for accuracy scores, especially if your dataset is not too large.
