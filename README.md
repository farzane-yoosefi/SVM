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
- *Soft margin*
- *Hinge loss*
- *Dual problem*
