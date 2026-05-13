<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/bdaf4e49-3f65-474b-a69e-1714406d6981" /># Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required libraries and load the employee churn dataset.
2. Preprocess the data and split it into training and testing sets.
3. Create and train the Decision Tree Classifier model using training data.
4. Predict the test results and evaluate the model accuracy.

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: VASHMITHA V
RegisterNumber: 212225240180

# Import required libraries
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report

# Create sample employee churn dataset
data = {
    'Age': [25,30,45,35,40,50,23,31,28,42,39,26,48,33,29,41],
    'Salary': [30000,40000,50000,45000,60000,65000,32000,41000,
               35000,58000,52000,33000,62000,43000,36000,54000],
    'Department': ['HR','IT','Finance','IT','HR','Finance','IT','HR',
                   'Finance','IT','HR','Finance','IT','HR','IT','Finance'],
    'Churn': ['Yes','No','No','Yes','No','No','Yes','No',
              'Yes','No','No','Yes','No','No','Yes','No']
}

# Convert into DataFrame
df = pd.DataFrame(data)

# Encode categorical data
le = LabelEncoder()

df['Department'] = le.fit_transform(df['Department'])
df['Churn'] = le.fit_transform(df['Churn'])

# Features and target
X = df[['Age', 'Salary', 'Department']]
y = df['Churn']

# Split data
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.3, random_state=42
)

# Create model
model = DecisionTreeClassifier()

# Train model
model.fit(X_train, y_train)

# Predict
y_pred = model.predict(X_test)

# Accuracy
accuracy = accuracy_score(y_test, y_pred)

# Print outputs
print("Accuracy:", round(accuracy, 2))

print("\nConfusion Matrix:")
print(confusion_matrix(y_test, y_pred))

print("\nClassification Report:")
print(classification_report(y_test, y_pred))
 
*/
```

## Output:
<img width="1920" height="1080" alt="Screenshot (138)" src="https://github.com/user-attachments/assets/e21e12e1-d33f-4c6e-a8d1-354549d5d6f4" />



## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
