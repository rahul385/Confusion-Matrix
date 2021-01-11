# Confusion-Matrix

### Table of Contents
1. [Blog Post](#Blog_Post)
2. [Sample Code](#code)

## Blog Post <a name="Blog_Post"></a>
Here is the link to my blog post that describes different aspects of Confusion Matrix.

[Confusion Matrix](https://rahulgupta1.medium.com/confusion-matrix-in-machine-learning-d15040776893)

## Sample Code <a name="code"></a>
```
# confusion matrix in sklearn
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
matrix = classification_report(actual,predicted,labels=[1,0])
print('Classification report : \n',matrix)

# Making a heatmap with percentages
sns.heatmap(matrix1/np.sum(matrix1), annot=True,fmt='.2%', cmap='Blues')

# Making a heatmap with labels
labels = ['True Neg','False Pos','False Neg','True Pos']
labels = np.asarray(labels).reshape(2,2)
sns.heatmap(matrix1, annot=labels, fmt='', cmap='Blues')
```

## Screenshots

***Screenshot 1:Heatmap with Labels***
![Screenshot 1]("https://github.com/rahul385/Confusion-Matrix/blob/master/Visualizations/Heatmap with Labels.png")

***Screenshot 2:Heatmap with percentages***
![Screenshot 2]('https://github.com/rahul385/Confusion-Matrix/blob/master/Visualizations/Heatmap with percentages.png')
