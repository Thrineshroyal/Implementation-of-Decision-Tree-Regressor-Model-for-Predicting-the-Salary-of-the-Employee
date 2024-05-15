# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm :
### 1. Initialize the dataset using the pandas library
### 2. Have a look at the dataset using df.head() and df.info() to make any changes
### 3. Convert the string columns to numerical values to fit in to the regressor 
### 4. Split the dataset to train and test and then fit that data to the DecisionTreeRegressor
### 5. Evaluate the model on metrics like mse and r2 score
### 6. Predict values of Salary using the trained model

## Programs :

```
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Thrinesh Royal.T
RegisterNumber:  212223230226
```

```python
import pandas as pd
data=pd.read_csv('Salary.csv')
data.head()
```
## Output :
![image](https://github.com/SANTHAN-2006/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/80164014/d57ee904-a124-4b46-bce7-fec41849776b)

```python
data.info()
```
## Output :
![image](https://github.com/SANTHAN-2006/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/80164014/9e2e1382-8ca4-4f40-8167-cf2b8844e575)


```python
data.isnull().sum()
```
## Output :
![image](https://github.com/SANTHAN-2006/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/80164014/b9ef8043-9b6a-414e-a4b3-783793c2fee7)


```python
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data['Position']=le.fit_transform(data['Position'])
data.head()
```
## Output :
![image](https://github.com/SANTHAN-2006/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/80164014/fdafe34e-2cd0-4238-961f-506a6f89fe36)


```python
x=data[["Position","Level"]]
y=data["Salary"]
```

```python
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
mse
```

## Output :
![image](https://github.com/SANTHAN-2006/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/80164014/1562adc4-2840-49e4-bee7-a400fec10b4b)


```python
r2=metrics.r2_score(y_test,y_pred)
r2
```
## Output :
![image](https://github.com/SANTHAN-2006/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/80164014/732622e1-efeb-4253-bbec-a50d6faa0ff2)


```python
dt.predict([[5,6]])
```
## Output :
![image](https://github.com/SANTHAN-2006/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/80164014/483c96c8-17a4-4e12-b96f-d0807998bec4)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
