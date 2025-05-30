# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import the standard libraries.
2. Upload the dataset and check for any null values using .isnull() function.
3. Import LabelEncoder and encode the dataset.
4. Import DecisionTreeRegressor from sklearn and apply the model on the dataset.
5. Predict the values of arrays.
6. Import metrics from sklearn and calculate the MSE and R2 of the model on the dataset.
7. Predict the values of array.
8. Apply to new unknown values.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: P KEERTHANA
RegisterNumber: 212223240069
*/
```

```
import pandas as pd
data=pd.read_csv('Salary.csv')
data.head()
```

![image](https://github.com/user-attachments/assets/67360494-ec63-438d-a459-83929d4ba946)

```
data.info()
```

![image](https://github.com/user-attachments/assets/587d1ea2-62ed-4e28-bbe4-bcfdcf026c8e)

```
data.isnull().sum()
```

![image](https://github.com/user-attachments/assets/190e3e3e-6c8d-46d6-ad85-3d7f87221b82)

```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
```

![image](https://github.com/user-attachments/assets/b120b2f9-5952-44b4-ad0d-bb3fae781ce0)

```
x=data[["Position","Level"]]
y=data["Salary"]
```
```
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

![image](https://github.com/user-attachments/assets/46232d33-8c3b-4271-95ea-cde4f04dd3f5)

```
dt.predict([[5,6]])
```

![image](https://github.com/user-attachments/assets/ba69af01-d1bc-48de-a925-91a242efc3e8)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
