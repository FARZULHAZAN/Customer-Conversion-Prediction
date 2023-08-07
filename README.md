Problem Statement.
You are working for a new-age insurance company and employ multiple outreach plans to sell term insurance to your
customers. Telephonic marketing campaigns still remain one of the most effective ways to reach out to people however they
incur a lot of cost. Hence, it is important to identify the customers that are most likely to convert beforehand so that
they can be specifically targeted via call. We are given the historical marketing data of the insurance company and are
required to build a ML model that will predict if a client will subscribe to the insurance.
Out of all 4 models 
XGBclassifier is the best it gives cross_val_score of 89.58 % 
AdaBoostClassifier of 89.51%
RandomForestClassifier gives 89.39%
LogisticRegression which gives 89.14%
least performed model is DecisionTreeClassifier of 87.18%

So according Extreme Gradient Boosting the feature importance should be:
1.Month
2.Duration 
3.Student (Job)
4.Education Qualification
5.Blue-Collar (Job)
6.Day
7.Single (Marital)
8.Services (Job)
9.Management (Job)
10.Age
11.Married (Marital)
12.Number of calls
13.Entrepreneur (Job)
14.Divorced (Marital)
15.Technician (Job)
16.Admin. (Job)
17.Unemployed (Job)
18.Self-Employed (Job)
19.Retired (Job)
