# California Test Score Data
## Clustering and Regression applied to the California Test Score Data
- Clustering: PCA, KMeans, Decision Tree, and Logistic Regression
- Regression : Linear, Lasso, and Ridge Regression

## Source
https://vincentarelbundock.github.io/Rdatasets/doc/AER/CASchools.html

## Description
The dataset contains data on test performance, school characteristics and student demographic backgrounds for school districts in California.
A data frame containing 420 observations on 14 variables.
The data used here are from all 420 K-6 and K-8 districts in California with data available for 1998 and 1999. 
Test scores are on the Stanford 9 standardized test administered to 5th grade students. 
School characteristics (averaged across the district) include enrollment, number of teachers (measured as “full-time equivalents”, number of computers per classroom, and expenditures per student. 
Demographic variables for the students are averaged across the district. 
The demographic variables include the percentage of students in the public assistance program CalWorks (formerly AFDC), the percentage of students that qualify for a reduced price lunch, and the percentage of students that are English learners (that is, students for whom English is a second language).

### Variables
- district: character. District code.
- school: character. School name.
- county: factor indicating county.
- grades: factor indicating grade span of district.
- students: Total enrollment.
- teachers: Number of teachers.
- calworks: Percent qualifying for CalWorks (income assistance).
- lunch: Percent qualifying for reduced-price lunch.
- computer: Number of computers.
- expenditure: Expenditure per student.
- income: District average income (in USD 1,000).
- english: Percent of English learners.
- read: Average reading score.
- math: Average math score.

## Clustering
### KMean Cluster Interpretation
#### Cluster 0:
    - Medium schools (Medium number of students, medium number of teachers).
    - Highest lunch assistance.
    - 2nd lowest number of computers.
    - 2nd highest expenditure.
    - Lowest income.
    - 2nd highest English scores.
    - Lowest Reading scores.
    - Lowest Math scores.
    
#### Cluster 1: 
    - Small schools with higher teacher to student ratio (smallest number of students, small number of teachers).
    - Lowest lunch assistance.
    - More computers than medium schools.
    - Highest expenditure.
    - Highest income.
    - Lowest English scores.
    - Highest Reading scores.
    - Highest Math scores.

#### Cluster 2: 
    - Small schools (small number of students, smallest number of teachers).
    - Low lunch assistance.
    - Lowest number of computers.   
    - Lowest expenditure.
    - 2nd highest income.
    - 2nd lowest English scores. 
    - 2nd highest Reading scores.
    - 2nd highest Math scores.
    
#### Cluster 3: 
    - Bigger schools (Large number of students, large number of teachers).
    - Medium lunch assistance.
    - Higher number of computers.
    - 2nd lowest expenditure.
    - 2nd lowest income.
    - Highest English scores.
    - 2nd lowest Reading scores.
    - 2nd lowest Math scores.

### Decision Tree Clustering
- Cluster 0: 90% of the cluster have greater than reading scores of  -0.34 and income less than or equal to 1.23.
- Cluster 1: 92% of the cluster have less than or equal to reading scores of  -0.34 and teachers 1.16.
- Cluster 2: 100% of the cluster have less than or equal to reading scores of  -0.34 and teachers greater than 1.16.
- Cluster 3: 85% of the cluster have greater than reading scores of  -0.34 and greater income 1.16.

### Logistic Regression Clusters
![alt text](https://github.com/natvalenz/schoolsScores/blob/main/roc.jpg)

### Does the clustering algorithm find good clusters that can be used for classification?
The clustering algorithm found good clusters. The error rate is small 0.017 and the ROC curve shows class 1 and 3 on top of each other with class 0 not too far off. Class 2 is the furthest but still has a 0.95.

## Regression
### Linear regression model using ordinary least squares method
Based on the results of MSE and RMSE there does not appear to be overfitting. 
The training MSE is lower than the testing MSE, but it could be argued that the difference is not significant. 
After tuning the model, the results should be improved.

### Which model is the best, OLS, Lasso, or Ridge regression?
Linear and Ridge regression are similar. The Lasso regression appears to have performed the worst.


