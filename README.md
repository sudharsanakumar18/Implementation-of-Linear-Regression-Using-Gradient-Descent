# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required library and read the dataframe.
2. Write a function computeCost to generate the cost function.
3. Perform iterations og gradient steps with learning rate.
4. Plot the Cost function using Gradient Descent and generate the required graph.

## Program:
```
Program to implement the linear regression using gradient descent.
Developed by:SUDHARSANA KUMAR S R 
RegisterNumber:212223240162

# Import required package
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("ex1.txt",header=None)
data
data.shape
plt.scatter(data[0],data[1])
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Population of City(10,000s)")
plt.ylabel("Profit ($10,000)")
plt.title("Profit Vs Prediction")
def computeCost(X,y,theta):
    m=len(y)
    h=X.dot(theta)
    square_err=(h-y)**2

    return 1/(2*m) * np.sum(square_err)
data_n=data.values
m=data_n[:,0].size
X=np.append(np.ones((m,1)),data_n[:,0].reshape(m,1),axis=1)
y=data_n[:,1].reshape(m,1)
theta=np.zeros((2,1))

computeCost(X,y,theta)
theta.shape
y.shape
X.shape
def gradientDescent(X,y,theta,alpha,num_iters):
  
  m=len(y)
  J_history=[]

  for i in range(num_iters):
    predictions=X.dot(theta)
    error=np.dot(X.transpose(),(predictions - y))
    descent=alpha * 1/m * error
    theta-=descent
    J_history.append(computeCost(X,y,theta))

  return theta, J_history
  
theta,J_history = gradientDescent(X,y,theta,0.01,1500)
print("h(x) ="+str(round(theta[0,0],2))+" + "+str(round(theta[1,0],2))+"x1")
plt.plot(J_history)
plt.xlabel("Iternations")
plt.ylabel("$J(\Theta)$")
plt.title("Cost function using Gradient Descent")
plt.scatter(data[0],data[1])
x_value=[x for x in range(25)]
y_value=[y*theta[1]+theta[0] for y in x_value]
plt.plot(x_value,y_value,color="r")
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Polpulation of City (10,000s)")
plt.ylabel("Profit (10,000s)")
plt.title("Profit Prediction")
def predict(x,theta):
  predictions= np.dot(theta.transpose(),x)
  return predictions[0]
  
predict1=predict(np.array([1,3.5]),theta)*10000
print("For population = 35,000, we predict a profit of $"+str(round(predict1,0)))

predict2=predict(np.array([1,7]),theta)*10000
print("For population = 70,000, we predict a profit of $"+str(round(predict2,0)))
```

## Output:
# Read CSV File:
![image](https://github.com/sudharsanakumar18/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/138849110/2915117a-adce-45db-8fd8-bd82b0a21080)

# Dataset shape:
![image](https://github.com/sudharsanakumar18/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/138849110/440c9881-e29b-411b-a5cb-b4b6d0421ce7)

# Profit Vs Prediction graph:
![image](https://github.com/sudharsanakumar18/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/138849110/0dd829bf-d703-448a-88e0-41e32d13784a)

# x,y,theta value:
![image](https://github.com/sudharsanakumar18/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/138849110/f9257cfa-1a60-4096-a170-116cef97f939)

# Gradient descent:
![image](https://github.com/sudharsanakumar18/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/138849110/4a28ae67-23a6-40b4-8a9b-711af1ba07ba)

# Cost function using Gradient Descent Graph:
![image](https://github.com/sudharsanakumar18/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/138849110/97530360-9459-4556-bda4-eadcff197b42)

# Profit Prediction Graph:
![image](https://github.com/sudharsanakumar18/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/138849110/2451e1d8-1360-4662-a0df-67f77705e7c4)

# Profit Prediction:
![image](https://github.com/sudharsanakumar18/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/138849110/7d15da08-f800-417a-9cb5-fb4648b9288e)

## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
