# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn
## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Start the program by importing required libraries.
2. Include the required dataset for the experiment.
3. Get the info of the data.
4. Split the given data as training and testing data
5. Import DecisionTreeClassifier to find y_pred,accuracy
6. End the program

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: SARANYA S
RegisterNumber:  212223110044
*/
```
```
import pandas as pd 
data=pd.read_csv('Employee.csv')
data.head()
```
## Output:
![image](https://github.com/user-attachments/assets/030e7989-b3b4-4666-a9cc-4e3ed9ea69e7)

```
data.info()
```
## Output:
![image](https://github.com/user-attachments/assets/e442aa24-a0b9-4b49-84ea-573ba6043746)

```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["salary"]=le.fit_transform(data['salary'])
data.head()
```
## Output:
![image](https://github.com/user-attachments/assets/b8d1fa12-aef0-43ef-aa99-2c4ae57ec450)

```
x=data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","Work_accident","promotion_last_5years","salary"]]
x.head()
```
## Output:
![image](https://github.com/user-attachments/assets/3b169b1c-587f-4b9a-96e4-c6e6230bde52)

```
y=data["left"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)
```
```
from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn.metrics import accuracy_score
accuracy=accuracy_score(y_test,y_pred)
accuracy
```
## Output:
![image](https://github.com/user-attachments/assets/381d7390-81ca-4de9-afd6-57a0d107af96)

```
dt.predict([[0.5,0.8,9,260,6,0,2]])
```
## Output:
![image](https://github.com/user-attachments/assets/c84dd53d-37cc-48ab-bd8c-5946be18eb11)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
