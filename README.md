# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Input: Independent variable X (e.g., hours studied) and dependent variable Y (e.g., marks scored).

Compute means: Calculate the mean of X and the mean of Y.

Calculate slope (m): Find the ratio of the sum of the products of the differences of X and Y from their means, to the sum of the squared differences of X from its mean.

Compute intercept (b): Subtract the product of the slope and the mean of X from the mean of Y.

Form the regression line: The equation is Y = m * X + b.

Plot results: Create a scatterplot and plot the regression line.

## Program:
```
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: Arunsamy D
RegisterNumber: 212224240016
```
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

stu_scores_df = pd.read_csv('/content/student_scores.csv')

x = stu_scores_df['Hours'].values
y = stu_scores_df['Scores'].values

x_mean = np.mean(x)
y_mean = np.mean(y)

numerator = 0
denominator = 0

# Calculating Slope m and y Intercept c # y = mx + c

# Calculating Slop m using Least Square Method m = ∑(x-i - x-mean)(y-i - y-mean)/∑(x-i - x-mean)


for i in range(len(x)):
  numerator += ( x[i] - x_mean ) * ( y[i] - y_mean ) #  ∑(x-i - x-mean)(y-i - y-mean)
  denominator += ( x[i] - x_mean)**2 # ∑(x-i - x-mean)


m = numerator/denominator # Slope

c = y_mean - m * x_mean # Intercept

print('Slope: ',m)
print('Y-intercept: ',c)

# Predicting values based on the slope m and intercept c 

y_predicted = m * x + c   # y = mx + c

print('Predicted values: ',y_predicted)

plt.scatter(x,y)
plt.plot(x,y_predicted,color='red')
plt.title('LINEAR REGRESSION GRAPH')
plt.xlabel('Hours Studied')    
plt.ylabel('Scores Obtained')  
plt.show()
```

## Output:

![image](https://github.com/user-attachments/assets/3a470059-4362-42d2-8598-fbe6225d5374)

## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
