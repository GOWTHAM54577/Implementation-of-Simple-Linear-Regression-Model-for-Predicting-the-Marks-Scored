# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. import the needed packages.
2. Assigning hours to x and scores to y.
3. Plot the scatter plot.
4. Use mse,rmse,mae formula to find the values.

## Program:
```
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: GOWTHAM N
RegisterNumber:  212223100008
*/
import pandas as pd
import numpy as np
from sklearn.metrics import mean_absolute_error,mean_squared_error
import matplotlib.pyplot as plt
dataset=pd.read_csv('student_scores.csv')
print(dataset)
# READ CSV FILES
dataset=pd.read_csv('student_scores.csv')
print(dataset.head())
print(dataset.tail())
# COMPARE DATASET
x=dataset.iloc[:,:-1].values
print(x)
y=dataset.iloc[:,1].values
print(y)
# PRINT PREDICTED VALUE
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=1/3,random_state=0)
from sklearn.linear_model import LinearRegression
reg=LinearRegression()
reg.fit(x_train,y_train)
y_pred = reg.predict(x_test)
print(y_pred)
print(y_test)
# GRAPH PLOT FOR TRAINING SET
plt.scatter(x_train,y_train,color='purple')
plt.plot(x_train,reg.predict(x_train),color='black')
plt.title("Hours vs Scores(Training set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
# GRAPH PLOT FOR TESTING SET
plt.scatter(x_test,y_test,color='red')
plt.plot(x_train,reg.predict(x_train),color='black')
plt.title("Hours vs Scores(Testing set)")
plt.xlabel("Hours")
plt.ylabel("Scores")
plt.show()
# PRINT THE ERROR
mse=mean_absolute_error(y_test,y_pred)
print('Mean Square Error = ',mse)
mae=mean_absolute_error(y_test,y_pred)
print('Mean Absolute Error = ',mae)
rmse=np.sqrt(mse)
print("Root Mean Square Error = ",rmse)
```
## Output:

Head:

![image](https://github.com/user-attachments/assets/c4e4750a-a839-471a-98bd-a4cc750df610)



Tail:

![image](https://github.com/user-attachments/assets/9872f274-5ba4-4097-91b6-a1076f9e74a8)



Array value of x:

![image](https://github.com/user-attachments/assets/612d7362-2258-4428-a507-af731af3cf1b)


Array value of y:

![image](https://github.com/user-attachments/assets/12476699-2251-47be-8b54-5b4fff295406)



Y prediction:

![image](https://github.com/user-attachments/assets/27a7b808-84e7-41f5-801c-0f6573e678e3)




Array value of Y test:

![image](https://github.com/user-attachments/assets/a52317cb-6690-44b3-8f57-c0a78aef3739)


Training set graph:



![image](https://github.com/user-attachments/assets/42263484-06b0-4ab2-a22d-e1d1e242f69c)






## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
