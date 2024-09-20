# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
STEP 1. Import the required libraries.
STEP2. Upload the csv file and read the dataset.
STEP 3. Check for any null values using the isnull() function.
STEP 4. From sklearn.tree inport DecisionTreeRegressor.
STEP 5. Import metrics and calculate the Mean squared error.
STEP 6. Apply metrics to the dataset, and predict the output.
## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: BALA MURUGAN S
RegisterNumber:  212223230027
*/

Import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()

data.info()

data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()

data["Position"]=le.fit_transform(data["Position"])
data.head()

x=data[["Position","Level"]]
x.head()

y=data[["Salary"]]

from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test, y_pred)
mse

r2=metrics.r2_score(y_test,y_pred)
r2

dt.predict([[5,6]])
```

## Output:
![Screenshot 2024-09-20 103623](https://github.com/user-attachments/assets/169916f9-ae94-41eb-bdd7-b6b77b2bf072)


![Screenshot 2024-09-20 103639](https://github.com/user-attachments/assets/0ddb804c-6518-44cb-b910-7f81c4c3f1c7)


![Screenshot 2024-09-20 103736](https://github.com/user-attachments/assets/742f2ac9-2b7c-4f47-9fca-43160cbe0211)


![Screenshot 2024-09-20 103649](https://github.com/user-attachments/assets/c5496e41-fdf0-42ed-a763-7e60b7752b56)


![Screenshot 2024-09-20 103655](https://github.com/user-attachments/assets/a88dde20-144a-4bc3-8f16-152e45809e94)


![Screenshot 2024-09-20 103708](https://github.com/user-attachments/assets/80bc7f01-e319-4279-a72a-d1268498bfdb)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
