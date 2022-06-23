## Titanic Dataset

### Model 1.0 - Logistic Regression

#### Load data

#### Study all the columns
    - PassengerId - no relation
    - PClass - already in grouped form
    - Name - can study after first model
    - Sex - can have a relation
    - Age - can be grouped into - Infant, Kid, Young, Adult, Old
    - SibSp - can be grouped into 3-4 classes i.e. 0, <2, <4, <6, <8, <10
    - Parch - can be grouped into 3-4 classes i.e. 0, <2, <4, <6, <8, <10
    - Ticket - numbers can be extracted and grouped in the second model
    - Fare - might be associated with compartments, can be grouped into Low, Low-Medium, Medium, Medium-High, High
    - Cabin - Can be classified by extracting first Letter

#### Target
    - Survived - Target variable

#### Drop the redundant/ columns
    - Name - No use in Model 1.0
    - PassengerId - No use
    - Ticket - No use in Model 1.0
    - Cabin - No use in Model 1.0

#### Upgradations for Model 2.0
    - Names, Cabin, Ticket

#### Grouping Columns, and filling NaN
    - Pclass - already in grouped form - [Done]
    - Sex - can have a relation - [Done]
    - Age - can be grouped into - Infant, Kid, Young, Adult, Old → Fill Null with Mode(Age) - [Done]
    - SibSp - can be grouped into 3-4 classes i.e. 0, 1, 2, <4, <6, <8 [Done]     
    - Parch - can be grouped into 3-4 classes i.e. 0, 1, 2, <4, <6 [Done]
    - Fare - might be associated with compartments, can be grouped into Low Low-Medium, Medium, Medium-High, High - [Done]
    - Embarked - already Categorised - [Done]


#### Relationship Exploration and Plotting
    - Distribution of Target Variable - Survived (Skewed towards 0)
    - Plotting y=target and x= various features


#### Encoding data
    - Dummy method of Pandas or One Hot encoding

#### Training & Testing
    - Checking Confusion Matrix and Accuracy

#### Result
'''
    [[158  20]
    [ 34  83]]

Accuracy = 0.8169491525423729
'''