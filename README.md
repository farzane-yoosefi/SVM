# SVM
>> These notes serve to demonstrate my machine learning knowledge to potential employers while also helping beginners learn complex concepts in simple terms.

**SVM** is a supervised machine learning model used to find the best possilbe boundary between classes.
it is useful when you want to do binary classification like spam not spam or cat vs. dog.
The main goal of SVM is to maximize the margin between two classes. But you maight get confused about what margin is.  
**Margin** is the empty space between decision boundary and the closest data point from the classes.  
**Support vectors** are those closest data points to the decision boundary.  
The larger the margin the better the model performs on the new unseen data.
## Key concepts of SVM 
- *Hyperplane* : This is a decision boundary which best separates the classes by maximizing the margin.
- *Support vectors* : They are the data points that are closest to the margin and directly "support" or define its width. They are the most critical points for determining the optimal hyperplanes.
- *Margin* : The distance between the decision boundary and the closest data points (the support vectors).
- *Kernel* : A function which maps the data into a high dimensional space. Somtimes the data can't be separated by a separate line like a circle of dots inside the dataset.A kernel transforms this data into a higher dimensional space so that it can separate using a single hyperplane.
- *Hard margin* : The ideal case in SVM ; It is the maximum size of margins with no support vectors within it.
- *Soft margin* :It is used when data is not perfectly separable , allows some misclassifications inside the margins and involves a penalty which balances width and errors.
- *Hinge loss* : While SVM maximizes the margin width, it uses hinge loss to punish the rule-breakers — these are:  
1. Data points on the wrong side of the decision boundary (not "decision tree"—that's a different algorithm).  
2. Data points inside the margin (even if on the correct side).
## How does SVM work?
The main goal is to find the best hyperplane which best separates the classes with the maximum margin between them.This margin the distance between the hyperplane and the support vectores.The best hyperplane is also known as **hard margin**. It maximizes the distance between the hyperplane and the nearest datapoint form both both classes. This ensures a clear separation between both classes. From the following figure we choose **l2** as hard margin.
<p align="center"><img src="https://github.com/farzane-yoosefi/SVM/blob/main/soft-margin.png" alt="Description" width="300" /></p>

## Implementing SVM Algorithm Using Scikit-Learn
We will predict whether cancer is Benign or Malignant using historical data about patients diagnosed with cancer.This data includes independent attributes such as tumor size, texture, and others. To perform this classification, we will use an SVM (Support Vector Machine) classifier to differentiate between benign and malignant cases effectively.
-  **load_breast_cancer() :** Loads the breast cancer dataset
-  **SVC(kernel="linear", C=1):** Creates a Support Vector Classifier with a linear kernel and regularization parameter C=1.
-  **svm.fit(X, y):** Trains the SVM model on the feature matrix X and target labels y.
-  **DecisionBoundaryDisplay.from_estimator():** Visualizes the decision boundary of the trained model with a specified color map.
-  **plt.scatter():** Creates a scatter plot of the data points, colored by their labels.
-  **plt.show():** Displays the plot to the screen.
### Step1 : 
Import the necessary libraries.
```python
from sklearn.datasets import load_breast_cancer
import matplotlib.pyplot as plt
from sklearn.inspection import DecisionBoundaryDisplay
from sklearn.svm import SVC
```
### step2 :
prepare the data
```python
cancer = load_breast_cancer()
X = cancer.data[:, :2]
y = cancer.target
```
### step 3:
Prepare the model:
```python
svm = SVC(kernel="linear", C=1)
svm.fit(X, y)
```
### Step 4:
 create and display the decision boundary of the trained SVM classifier
```python
DecisionBoundaryDisplay.from_estimator(
        svm,
        X,
        response_method="predict",
        alpha=0.8,
        cmap="Pastel1",
        xlabel=cancer.feature_names[0],
        ylabel=cancer.feature_names[1],
    )
```
### Step 5 :
See the result.
```python
plt.scatter(X[:, 0], X[:, 1], 
            c=y, 
            s=20, edgecolors="k")
plt.show()
```

