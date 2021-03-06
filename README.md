# Confusion-Matrix

<p align = 'center'><img src = 'logo.png', height=300, width =300></p>

### Table of Contents
1. [Blog Post](#Blog_Post)
2. [Sample Code](#code)
3. [Visualizations](#image)
4. [Licensing, Authors, and Acknowledgements](#licensing)

## Blog Post <a name="Blog_Post"></a>
Here is the link to my blog post that describes different aspects of Confusion Matrix.

[Confusion Matrix](https://rahulgupta1.medium.com/confusion-matrix-in-machine-learning-d15040776893)

## Sample Code <a name="code"></a>

A Confusion Matrix is an N x N matrix used for evaluating the performance of a classification model, where N is the number of target classes. The matrix compares the actual target values with those predicted by the machine learning model. This gives us a holistic view of how well our classification model is performing and what kinds of errors it is making.

```
import seaborn as sns
import numpy as np
import matplotlib.pyplot as plt
from sklearn.metrics import confusion_matrix
from sklearn.metrics import classification_report

# actual values
actual = [1,0,0,1,0,0,1,0,0,1]
# predicted values
predicted = [1,0,0,1,0,0,0,1,0,0]

# confusion matrix
matrix = confusion_matrix(actual,predicted, labels=[1,0])
print('Confusion matrix : \n',matrix)

# outcome values order in sklearn
tp, fn, fp, tn = confusion_matrix(actual,predicted,labels=[1,0]).reshape(-1)
print('Outcome values : \n', tp, fn, fp, tn)

# classification report for precision, recall f1-score and accuracy
matrix1 = classification_report(actual,predicted,labels=[1,0])
print('Classification report : \n',matrix)


# Making a heatmap with percentages
plt.subplot(2,1,1)
sns.heatmap(matrix/np.sum(matrix), annot=True,fmt='.2%', cmap='Blues');

# Making a heatmap with labels
plt.subplot(2,1,2)
labels = ['True Neg','False Pos','False Neg','True Pos']
labels = np.asarray(labels).reshape(2,2)
sns.heatmap(matrix, annot=labels, fmt='', cmap='Blues');
```

## Screesnshots <a name="image"></a>

***Screenshot 1:Heatmap with Labels***

![Screenshot 1](https://github.com/rahul385/Confusion-Matrix/blob/master/Visualizations/Heatmap_with_Labels.png)

***Screenshot 2:Heatmap with percentages***

![Screenshot 2](https://github.com/rahul385/Confusion-Matrix/blob/master/Visualizations/Heatmap_with_Percentages.png)

## Licensing, Authors, Acknowledgements <a name="licensing"></a>
Author: Rahul Gupta Copyright 2020

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
