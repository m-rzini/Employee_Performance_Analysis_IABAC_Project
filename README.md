 # __INX Future Inc. Employee Performance Analysis Project__

 <h2>Certified Data Science Final Project</h2>
 
  <table align="" border="1" cellpadding="8" cellspacing="0">
    <tr>
      <th>REP Name:</th>
      <td>DataMites™ Solutions Pvt Ltd</td>
    </tr>
    <tr>
      <th>Venue Name:</th>
      <td>Open Project</td>
    </tr>
    <tr>
      <th>Exam Country:</th>
      <td>India</td>
    </tr>
    <tr>
      <th>Assessment ID:</th>
      <td>E10901-PR2-V18</td>
    </tr>
    <tr>
      <th>Module:</th>
      <td>Certified Data Scientist - Project</td>
    </tr>
    <tr>
      <th>Language:</th>
      <td>English</td>
    </tr>
    <tr>
      <th>Exam Format:</th>
      <td>Open Project- IABAC™ Project Submission</td>
    </tr>
    <tr>
      <th>Submission Deadline Date:</th>
      <td>23-Jan-2024</td>
    </tr>
    <tr>
      <th>Submission Deadline Time:</th>
      <td>23:59 Hrs [IST]</td>
    </tr>
    <tr>
      <th>Candidate Name:</th>
      <td>Mohammed Rzini</td>
    </tr>
    <tr>
      <th>Candidate Email:</th>
      <td>mohammed.rzini@yahoo.fr</td>
    </tr>
    <tr>
      <th>Registered Trainer:</th>
      <td>Ashok Kumar A</td>
    </tr>
    <tr>
      <th>Project Assessment:</th>
      <td>IABAC™</td>
    </tr>
    
  </table>
  

# __Project Summary__

#### __Dataset Description__
- The information utilized in this project originates from the dataset offered by IABAC for an imaginary company named INC Future Inc. Within this dataset, there is a collection of employee profiles encompassing diverse features, including both categorical and numerical attributes. The primary objective is to forecast the performance rating of employees based on the provided feature values.
 - You can access the dataset from here -> http://data.iabac.org/exam/p2/data/INX_Future_Inc_Employee_Performance_CDS_Project2_Data_V1.8.xls
 - No external data is needed for the purpose of this project
 - The data set contains ordinal, nominal and numerical values as features and the target variable i.e Performance rating is again an ordinal variable.
#### __The following are the project goals:__
    1. Department wise performance 
    2. Three most important features 
    3. A trained machine learning model to predict the target variable
    4. Recommandations to imporve employee performance based on analysis and inferences
- The data set is a structured labelled dataset containing 1200 records and 27 features and a target variable in total
- Feature count suggests that 11 of these features are quantitative and 16 of these features are qualitative features
#### __Analysis techniques used:__
    - Distribution analysis - pandas and kernal density estimate plots
    - Correlation analysis - heatmaps
    - Analysis by visualization - univariate analysis using pandas yprofiling and bivariate analysis
#### __Data Processing:__
    - One hot encoding has been performed on the categorical  features using pandas get_dummies() method
    - The dataset was imbalanced as seen from the value_counts() of the target variable 
    - A combination of SMOTE and RandomUnderSampling has been used to give a better balanced dataset without falling into the traps or cons of simpling over sampling or undersampling the data
    - Feature and target splits have been performed by using pandas .iloc for data slicing
    - Training and validation split were preformed usign sklearn's train_test_split
#### __Machine learning:__
    - After preprocessing the data the cross validation has been performed on each of the supervised machine learning algorithms namely Logistic regression, RandomForestClassifier, GradientBoostingClassifier, Multilayer Perceptron, Support Vector Classifier, XGBoostClassifier, Gaussian Naive Bayes and K-Nearest Neighbours and an unsupervised machine learning algorithm K-means clustering. The validation score evidently gave out __GradientBoostingClassifier__ and __XGBClassifier__ to be the best performing algorithms
    - Hyperparmeter tuning was done on both of the above chosen ML models using RandomizedSearchCV and an accuracy of 91% was achieved although a higher compute using GridSearchCV would give much better results for future reference
#### __Important Features:__
    - The top three important features were chosen by using RandomForestClassifier and train the model and then using its .feature_importance_ attribute once the model has been trained to gather insight on which features have the highest predictive value
    
## __Features of the dataset__
### __Categorical Features__

The categorical features further classify themselves into ordinal values, nominal values  in the data set.

- Gender
- EducationBackground
- MaritalStatus
- EmpDepartment
- EmpJobRole
- BusinessTravelFrequency
- OverTime
- EducationLevel
- EmpEnvironmentSatisfaction
- EmpJobLevel
- EmpJobSatisfaction
- EmpJobInvolvement
- EmpRelationshipSatisfaction
- WorkLifeBalance
- Attrition

### __Numerical Features__
These are a set of continuous values the change for one data point to the other.

- Age
- DistanceFromHome
- EmpHourlyRate
- NumCompaniesWorked
- EmpLastSalaryHikePercent
- TotalWorkExperienceInYears
- TrainingTimesLastYear
- ExperienceYearsAtThisCompany
- ExperienceYearsInCurrentRole
- YearsSinceLastPromotion
- YearsWithCurrManager

### __Target__
This is the target to be predicted and the data type here is again categorical that is ordinal to be specific.
- PerformanceRating


# Analysis

## Data distribution of Variables

### __Categorical features__
1. Gender distribution: __60.4%__ male (725) and __39.6%__ female (475)<br>
2. Education Background:
    * Life sciences: __41%__ (492)
    * Medical: __32%__ (384)
    * Marketing: __11.4%__ (137)
    * Technical Degree: __8.3%__ (100)
    * Human Resources: __1.8%__ (21)
    * Others: __5.5%__ (66)
3. Marital Status : 
    * single : __45.7%__ (584)
    * Married : __32%__ (384)
    * Divorced : __22.3%__ (268)
4. Employee Department:
    * __31.1%__ of the people work in sales (373)
    * __30.1%__ of the people work in Development (361)
    * __28.6%__ of people work in Research and development (343)
    * __4.5%__ in HR (54)
    * __4.1%__ in Finance (49)
    * __1.7%__ in Data Science (20)
<br>
5. There are <b>19</b> Unique Employee Job Roles in the organization with __22.5%__ Employees working as Sales executive counting as the highest number of employees in any role followed by Developers which are at __19.7%__ followed by the rest with each role not exceeding __8%__ of the total employees
<br>
6. Out the given population only __18.5%__ of the employee's travel frequently, __70.5%__ of employees do still travel although rarely and the rest do not travel
<br>
7. __29.4%__ of employees do Overtime
<br>
8. __85.2%__ employees does not have attrition

### Numerical features
1. The age distribution here can be considered gaussian given its skewness and kurtosis ranging in __|1.96|__
2. The highest number of employees fall in the age group of __30__ to __45__.
3. The most common education level among employees is __3__ or as described in the data definitions __Bachelors__
4. The two most common employee environment satisfaction rates are __3__ and __4__ i.e. __high__ and __very high__ so the environment of the company seems highly satisfactory for the employees
5. The mean hourly rate is __65.98__ with most of the employees earning between the range of 60 to 95
6. The most common job involvement rating is 3 i.e. __high__ so the employees at this company have a good Job Involvement rate
7. The distribution also states that around __72%__ of the employees are in the preliminary job roles of 1 and 2
8. Around __60%__ of the employees are __highly__ or __very highly__ satisfied with their jobs

## Data Analysis through visualizations

### Inference from the Kernal Density Estimate and LinePlots
1. The better the employee's worklife balance the better he/she performs
2. Trainings should be kept at a moderate amount as a very high amount of training is resulting in reducing employee performance
3. The Employee relationship should be kept in control and not very low or very high as that affects the performance rating of the employee
4. The higher the environment satisfaction the higher is the employee performance 
5. Employees with salary hike above 20 % tend to have a drastic increase in their performance

### Inference from the corr() method
1. The highly correlated features are TotalYearsOfExperience and EmpJobLevel with __0.78%__
2. ExperienceYearsInCurrentRole, ExperienceYearsAtThisCompany and ExperienceYearsInCurrentRole, YearsWithCurrManager are also subsequently highly correlated with a range of [__0.72%__ to __0.76%__]
3. There is also a considerable correlation between ExperienceYearsAtThisCompany and YearsSinceLastPromotion (__0.62%__) although from the subsequent heatmaps and Line Charts is clear that someone with experience higher than 35 years with this company or someone as new as having less than 15 years with this company is likely to get a promotion as compared to someone who has been associated with the company for more than 20 or less than 35 years.


# Project Goals
## __1 : Department Wise Performance Rating Inferences__

1. __Sales Department__
    - Most of the employees have excellent (3) performance rating
    - Younger age group performs comparatively better than the older age group although the variation is not high
    - Job satisfaction and Environment satisfaction is directly correlated to performance rating so the higher the job and environment satisfaction the higher is the performance
    - Sales Executives and Representatives perform better than their managers in general
    - New employee or the oldest ones have better performance as compared to those who have moderate experience with current company
    - Those who have less experience in current role or are relatively new to their current role out perform the experienced ones
    - Those who have been recently promoted perform better than those whose promotion has not happend for more than 4 years now
    
2. __Development Department__
    - Most of the employees have excellent (3) performance rating
    - Younger age group or the oldest age group out performs the middle aged employees
    - Gender wise performance says female perform slightly better than male
    - Job satisfaction and Environment satisfaction is directly correlated to performance rating so the higher the job and environment satisfaction the higher is the performance
    - Developers and Tech. lead's out perform other job roles on an average
    - Experience in current role does not have much effect on the performance rating of employees 
    - Those who have been recently promoted perform better than those whose promotion has not happend for more than 4 years now
    
3. __Research & Development Department__
    - Most of the employees have excellent (3) performance rating
    - The youngest age group of upto 25 out-performs other age groups by a huge margin
    - Gender wise performance says female perform slightly better than male
    - Environment satisfaction is directly correlated to performance rating so the higher the environment satisfaction the higher is the performance
    - New employee or the oldest ones have better performance as compared to those who have moderate experience with current company
    - Those who have less experience in current role or are relatively new to their current role out perform the experienced ones
    - Those who have been recently promoted perform better than those whose promotion has not happend for more than 4 years now
    
4. __Human Resources__
     - Most of the employees have excellent (3) performance rating
     - age groups upto 30 out perform older age groups
     - Gender wise performance says female out perform male by some considerable margin
     - Environment satisfaction is directly correlated to performance rating so the higher the environment satisfaction the higher is the performance
     
5. __Finance Department__
    - Considerably some amount of low performing employees are present as compared to other departments but the rest do have excellent performance
    - Age group wise those upto 41-50 have good performance
    - Job satisfaction to performance rating is way below the considerable margin
    - Environment satisfaction is directly correlated to performance rating so the higher the environment satisfaction the higher is the performance
    - Sales Executives and Representatives perform better than their managers in general
    - New employee or the oldest ones have better performance as compared to those who have moderate experience with current company
    - Those who have less experience in current role or are relatively new to their current role out perform the experienced ones
    - Those who have been recently promoted perform better than those whose promotion has not happend for more than 4 years now
    
    
6. __Data Science Department__
    - Most of the employees have excellent (3) performance rating
    - All age groups have an excellent peformance rating
    - Job satisfaction and Environment satisfaction is directly correlated to performance rating so the higher the job and environment satisfaction the higher is the performance
    - Those with low experience in current role tend to perform higher which is relatable as these are the ones trying to get the hang of the department.
    
    
## __2 : Three most important features__
### __Most Important Features according to Random Forest Classifier and XGBoost__

RFClassifier and XGBoost are two of the sharpest methods to find out which features have better predictive value as compared to others using its attribute __feature_importance___. These tree based ensamble models give out an array of values containing the importance of each feature for the prediction of our targe variables

- ___According to analysis the following 3 features are the most important___
1. ___EmpLastSalaryHikePercent___ - Last salary hike percentage of employee
2. ___EmpEnvironmentSatisfaction___ - How satisfied an employee is with the work environment
3. ___YearsSinceLastPromotion___ - How recent is the employee's last promotion

## __3 : Trained machine learning model to predict the target i.e. Performance Rating__
- K-Fold Cross validation has been performed on each of the following machine learning algorithms:
    1. Logistic regression
    2. RandomForestClassifier 
    3. GradientBoostingClassifier 
    4. Multilayer Perceptron 
    5. Support Vector Classifier 
    6. XGBoostClassifier 
    7. Gaussian Naive Bayes 
    8. K-Nearest Neighbours 
    9. K-means clustering. 
    
- The validation score evidently gave out __GradientBoostingClassifier__ and __XGBClassifier__ to be the best performing algorithms. - - Hyperparmeter tuning was done on both of the above chosen ML models using RandomizedSearchCV and an accuracy of 91% was achieved although a higher compute using GridSearchCV would give much better results for future reference
- Results of trained machine learning models
    1. ___GradientBoostingClassifier - 91% accuracy___
    2. ___XGBClassifier - 92% accuracy___
    
## __4 : Recommandations to improve employee performance__
- Enhancing the work environment is paramount for fostering greater employee satisfaction. This crucial factor consistently emerges as the most pivotal element in all analyses, promising substantial enhancements in overall employee performance.

- Introducing a systematic salary and promotion review mechanism can significantly uplift employee morale, reinforcing ethical standards and integrity. This initiative is poised to contribute positively to overall employee performance.

- Striking a better work-life balance has demonstrated positive correlations with increased employee performance, as evident in departmental analyses. Implementing strategies to support this balance can yield tangible benefits.

- Regularly reassessing roles, perhaps every couple of years, is a proven strategy to elevate employee performance. This approach ensures that job roles stay dynamic and aligned with evolving skills and organizational needs.

- Gender diversity can be leveraged to boost Human Resources performance by actively recruiting more female employees. Analysis indicates that female HR professionals tend to exhibit notably superior performance, offering a valuable avenue for improvement.

- Strategic restructuring of the work environment, along with periodic role and salary revisions, should prioritize the finance department. Given its higher proportion of underperforming employees, this targeted approach aims to address and improve performance disparities within the department.
