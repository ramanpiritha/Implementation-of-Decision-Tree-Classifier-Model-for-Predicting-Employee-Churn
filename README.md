# Ex.No: 08-Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
STEP 1 - Start

STEP 2 - attach the given data file

STEP 3 - now find the satisfaction level of employee data

STEP 4 - find the accuracy and new predict value

STEP 5 - Stop



## Program:
Developed by: Piritharaman R

RegisterNumber: 212223230148
```
import pandas as pd
data=pd.read_csv("Employee.csv")
data.head()
```

## Output:
![image](https://github.com/user-attachments/assets/a861a4df-ba59-42a4-be81-90e484413011)

```
df.info()
```
## Output:

![image](https://github.com/user-attachments/assets/e5906ef5-492c-4f9e-8506-3d5a7c4cd658)

```
df["left"].value_counts()
```
## Output:

![image](https://github.com/user-attachments/assets/b8b959ee-0f55-47a0-a70a-90c433cb728b)
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
```
```
data["salary"]=le.fit_transform(data["salary"])
data.head()
```
## Output:
![image](https://github.com/user-attachments/assets/84bd58ea-9bba-47ba-a588-d021f4275416)

```
x=data[["satisfaction_level","last_evaluation","number_project","average_montl
y_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]
x.head()
```
## Output:

![image](https://github.com/user-attachments/assets/a84c6e91-0511-4034-8413-838a551365a9)
```
y=data["left"]
y
```
## Output:

![image](https://github.com/user-attachments/assets/01530778-0fac-499f-8b1b-da4325ed0300)
```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,
random_state=100)
```
```
from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
```
```
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
## Output:
![image](https://github.com/user-attachments/assets/1b0eacbf-b822-41d0-a204-f629d3741824)

```
dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```

## Output:

![image](https://github.com/user-attachments/assets/d2b423d2-f408-4a75-a04e-3740966c16a1)


## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
