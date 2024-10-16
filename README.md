# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required libraries.
2. Upload and read the dataset.
3. Check for any null values using the isnull() function.
4. From sklearn.tree import DecisionTreeClassifier and use criterion as entropy.
5. Find the accuracy of the model and predict the required values by importing the required module from sklearn. 

## Program
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: Tharika S
RegisterNumber: 212222230159  
*/
```
```
import pandas as pd
data=pd.read_csv("/content/Employee.csv")
data.head()
```
## Output:
![image](https://github.com/user-attachments/assets/3c33b9db-ea7b-4875-bb9f-b596e0b03801)

```
data.info()
```
## Output:
![image](https://github.com/user-attachments/assets/06b6b024-8e23-4e3a-baa0-452a245b8c0c)
```
data.isnull().sum()
```
## Output:
![image](https://github.com/user-attachments/assets/7a86b95e-2014-47b6-860d-c0121db1a4ba)
```
data["left"].value_counts()
```
## Output:
![image](https://github.com/user-attachments/assets/144f0232-b81f-4263-af37-10dfa87c8706)
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()
```
## Output:
![image](https://github.com/user-attachments/assets/1c0ea34f-11fb-4f7f-84b1-78f5b5a67893)

```
x=data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]
x.head()
y=data["left"]
x.head()
```
## Output:
![image](https://github.com/user-attachments/assets/0b3596cf-f064-4914-bba8-e799922e6648)

```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)
from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```
## Output:
![image](https://github.com/user-attachments/assets/fd181bcb-24de-4ec5-929b-b8505613f5fa)



## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
