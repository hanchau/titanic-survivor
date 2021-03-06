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
- [[158  20]
- [ 34  83]]
- Accuracy = 0.8169491525423729

#### SHAP explainer
1. Being Upper/Lower Female --> positive/negative 
2. Being Female/Male --> positive/negative
3. Having/Not having <=1 sibling/spouce -->  positive/negative
4. Being/Not being Young/Adult --> negative/positive
5. Being low class --> positive (no negative relation)
6. etc


### Model 1.1 - Decission Trees and Random Forests

#### Clearning
    - Same as that of Logistic Regressino
    - Same dummies are used
    - Pclass is broken into dummies (not in Model 1.0)

#### Result
- [[143  28]
- [ 28  96]]
- Accuracy - 0.8101694915254237


### Model 1.2 - Naive Bayes

#### Result
    - GaussianNB
        - [[ 10 170]
        - [  2 113]]
        - Accuracy -  0.41694915254237286
    - BernoulliNB
        - [[149  31]
        - [ 25  90]]
        - Accuracy -  0.8101694915254237
    - MultinomialNB
        - [[156  24]
        - [ 34  81]]
        - Accuracy -  0.8033898305084746
    - CategoricalNB
        - [[149  31]
        - [ 25  90]]
        - Accuracy -  0.8101694915254237
    - ComplementNB
        - [[150  30]
        - [ 29  86]]
        - Accuracy -  0.8

### Reference URL
    - https://medium.com/analytics-vidhya/your-guide-for-logistic-regression-with-titanic-dataset-784943523994

### Issues
1. the dummy variable are not strictly independent --> using naiive bayes can be an issue [because of underlying independence assumption]
