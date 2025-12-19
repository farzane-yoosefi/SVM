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
The main goal is to find the best hyperplane which best separates the classes with the maximum margin between them.This margin the distance between the hyperplane and the support vectores.The best hyperplane is also known as **hard margin**. It maximizes the distance between the hyperplane and the nearest datapoint form both both classes. This ensures a clear separation between both classes. From the follong figure we choose l2 as hard margin.
