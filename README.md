                       ********Adult Income Prediction******
     
- This dataset contains information about individuals from the 1994 U.S. Census database, including their age, education, occupation, marital status, race, gender and whether they have an annual income of more than 50K dollars. The dataset is used for exploring and demonstrating data pre-processing and machine learning techniques.


- Data Source
  
- The dataset was extracted from the U.S. Census Bureau database by Barry Becker and donated to the UCI Machine Learning Repository in 1996. It is also known as the “Census Income” dataset or simply the “Adult” dataset.

- The original data source can be found here: http://www.cs.toronto.edu/~delve/data/adult/desc.html

- The UCI Machine Learning Repository page can be found here: https://archive.ics.uci.edu/ml/datasets/Adult

**Data Description**
- The dataset consists of 48,842 instances and 15 attributes (14 features and 1 target). The target attribute is the income class, which has two possible values: “<=50K” or “>50K”. The features are:

- age: The age of the individual in years (numeric)
- workclass: The type of employer the individual has (categorical)
- Possible values: Private, Self-emp-not-inc, Self-emp-inc, Federal-gov, Local-gov, State-gov, Without-pay, Never-worked
- fnlwgt: The final weight of the individual, which is the number of people the census takers believe that observation represents (numeric)
- education: The highest level of education achieved by the individual (categorical)
- Possible values: Bachelors, Some-college, 11th, HS-grad, Prof-school, Assoc-acdm, Assoc-voc, 9th, 7th-8th, 12th, Masters, 1st-4th, 10th, Doctorate, 5th-6th, Preschool
- education-num: The numerical value corresponding to the education level (numeric)
- marital-status: The marital status of the individual (categorical)
- Possible values: Married-civ-spouse, Divorced, Never-married, Separated, Widowed, Married-spouse-absent, Married-AF-spouse
- occupation: The occupation of the individual (categorical)
- Possible values: Tech-support, Craft-repair, Other-service, Sales, Exec-managerial, Prof-specialty, Handlers-cleaners, Machine-op-inspct, Adm-clerical,Farming-fishing, Transport-moving, Priv-house-serv, Protective-serv, Armed-Forces
- relationship: The relationship status of the individual (categorical)
- Possible values: Wife,Husband, Not-in-family, Own-child, Unmarried, Other-relative
- race: The race of the individual (categorical)
- Possible values: White, Asian-Pac-Islander, Amer-Indian-Eskimo, Other, Black
- sex: The gender of the individual (categorical)
- Possible values: Female,Male
- capital-gain: The capital gain of the individual in dollars (numeric)
- capital-loss: The capital loss of the individual in dollars (numeric)
- hours-per-week: The average number of hours the individual works per week (numeric)
- native-country: The native country of the individual (categorical)
- Possible values: United-States,Cambodia, England,Puerto-Rico, Canada, Germany, Outlying-US(Guam-USVI-etc), India, Japan,Greece,South, China,Cuba,Iran,Honduras, Philippines, Italy, Poland,Jamaica,Vietnam,Mexico, Portugal,Ireland, France,Dominican-Republic, Laos,Ecuador,Taiwan,Haiti,Columbia,Hungary Guatemala,Nicaragua, Scotland,Thailand,Yugoslavia El-Salvador, Trinadad&Tobago Peru,Hong,Kong Holand-Netherlands

  Data Analysis
  
_The dataset can be used for various data analysis tasks such as:_
- Identifying the duplicate and removing: You can use the .duplicated () method to check if a row is duplicated or not. It returns a boolean Series indicating whether each row is a duplicate or not. You can also use the .drop_duplicates () method to remove the duplicate rows from your DataFrame1.
- Identifying the Missing number and inconsistence values and addressing them respectively: You can use the .isnull () method to check if a value is missing or not. It returns a boolean value, either True or False. You can also use the .sum () method to count how many missing values you have in each column2. To address the missing values, you have some options, such as:
- Removing the rows or columns that contain missing values using the .dropna () method1.
- Replacing the missing values with a specific value, such as zero, mean, median, or mode using the .fillna () method1.
- Interpolating the missing values using a linear or other method using the .interpolate () method2.
- Data pre-processing to handle missing values, outliers and categorical encoding
- Explaining the X and y split making dataset ready for machine learning: To split your dataset into X (features) and y (target), you need to identify which column is your target variable and which columns are your features

Exploratory data analysis to understand the distribution and relationship of the features and the target:
Heatmap
![image](https://github.com/davegbade/Project-2-Machine-Learning.ipynb/assets/34641995/6aa10b7c-d57f-40eb-af60-5d7dc2aaa0cb)
Heatmaps are a great way of finding the collinearity of the data and help distinguish which rows or columns should or should not be included as part of your results. If the objective is to create several predictor models, this will help you filter any dependent variables that are collinear.

Histplot
![image](https://github.com/davegbade/Project-2-Machine-Learning.ipynb/assets/34641995/b86d77cd-833c-43d7-a533-3624a114f3f3)
A histogram is basically used to represent data provided in a form of some groups.It is accurate method for the graphical representation of numerical data distribution.It is a type of bar plot where X-axis represents the bin ranges while Y-axis gives information about frequency.

**Visualizations from your analysis**
Barplot
![image](https://github.com/davegbade/Project-2-Machine-Learning.ipynb/assets/34641995/516f5b9d-b095-47b2-bd77-35f036fae27d)
- The barplot shows the distribution of income levels across different age groups and races. The x-axis represents the income category, either above or below 50k per year. The y-axis represents the average age of the individuals in each category. The hue represents the race of the individuals, either white, black, Asian or other.

- The barplot reveals that the majority of individuals with income above 50k are more than 40 years old, indicating that higher income is associated with older age. It also shows that white individuals have the highest proportion of income above 50k, followed by black individuals. Assian and other individuals have the lowest proportion of income above 50k, suggesting that there are racial disparities in income distribution.

- The stakeholder can use this information to understand the demographic characteristics of the income groups and to identify potential areas for improvement or intervention. For example, the stakeholder may want to explore the reasons behind the racial gaps in income and to design policies or programs that can promote economic equality and opportunity for all races. Alternatively, the stakeholder may want to target younger individuals with lower income and provide them with education, training or mentoring that can help them increase their earning potential and career prospect

**Boxplot**

![image](https://github.com/davegbade/Project-2-Machine-Learning.ipynb/assets/34641995/ce2e338a-80d2-41ba-929f-836710427d27)

- The boxplot shows the variation of age across different income levels and races. The x-axis represents the income category, either above or below 50k per year. The y-axis represents the age of the individuals in each category. The hue represents the race of the individuals, either white, black, Asian or other.

- The boxplot reveals that the older white individuals have a higher income than the other races, as shown by the higher position and larger size of their box in the above 50k category. This means that they have a higher median age, as well as a wider range of ages, than the other races in the same income group. This could indicate that they work longer or have more experience than the other races, which may contribute to their higher income. It also shows that the younger white individuals have a lower income than the other races, as shown by the lower position and smaller size of their box in the below 50k category. This means that they have a lower median age, as well as a narrower range of ages, than the other races in the same income group. This could indicate that they have less education or skills than the other races, which may limit their income potential.

- The stakeholder can use this information to understand the age variation within and between the income groups and races and to identify potential factors that influence income levels. For example, the stakeholder may want to investigate the role of education, skills, experience, seniority, occupation or industry in determining income and to design policies or programs that can enhance these factors for all races. Alternatively, the stakeholder may want to address the issues of age discrimina

 Countplot
![image](https://github.com/davegbade/Project-2-Machine-Learning.ipynb/assets/34641995/a07e8782-589d-446c-9ce4-7d5d878e3994)


The countplot function is used to show the counts of observations in each categorical bin using bars12. It is similar to a histogram, but for categorical variables instead of quantitative variables. The function is used to show the observational count in different category-based bins with the help of bars2. The basic API and options are identical to those for barplot()1.

# Plot the bar chart
sns.barplot(x='educational-num', y='age', data=df2)
![image](https://github.com/davegbade/Project-2-Machine-Learning.ipynb/assets/34641995/c2d08416-c904-40c2-8cbc-552d093fe3c5)

Showing correlation between Age and Education.

**MODELLING AND EVALUATION**
-**KNN Model**


![image](https://github.com/davegbade/Project-2-Machine-Learning.ipynb/assets/34641995/6b3d02a1-82f9-453c-a0be-71d9fbe6a930)

- confusion matrices
  ![image](https://github.com/davegbade/Project-2-Machine-Learning.ipynb/assets/34641995/1fac5334-ef8a-4186-acae-ae7d12b8bf0f)

  ![image](https://github.com/davegbade/Project-2-Machine-Learning.ipynb/assets/34641995/1c1e1b9f-f53a-4c46-9e87-410f2932de89)

**  *****Decision Tree Classifier**********




Feature engineering to create new features or transform existing ones
Feature selection to identify the most relevant features for the prediction task
Model building and evaluation to apply different machine learning algorithms and compare their performance
References
Becker,B., & Ichino,A. (1998). Income Classification with Fuzzy Rule-Based Systems. In Proceedings of Joint Conference on Information Sciences (pp. 220–223).

Kohavi,R. (1996). Scaling Up the Accuracy of Naive-Bayes Classifiers: A Decision-Tree Hybrid. In Proceedings of the Second International Conference on Knowledge Discovery and Data Mining (pp. 202–207).

Lichman,M. (2013). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml]. Irvine, CA: University of California, School of Information and Computer Science.


The stakeholders for the “Adult” dataset are researchers and data scientists who are interested in exploring and demonstrating data pre-processing and machine learning techniques. The problem that this dataset is trying to solve is predicting whether a given adult makes more than $50,000 a year based on attributes such as education, hours of work per week, etc. This is a classification problem that can be used to explore techniques for imbalanced classification1.

Strengths:

The model can accurately predict whether a given adult makes more than $50,000 a year based on the available attributes.
The model can be used to identify which attributes are most important for predicting income level.
Limitations:

The model may have high false positive and false negative rates, which can affect the accuracy of the predictions.
The model may not be able to capture all of the relevant information in the dataset, which can lead to inaccurate predictions.
It is important to keep these strengths and limitations in mind when using the model to make predictions. Stakeholders should be aware of the potential limitations of the model and take steps to mitigate any negative impacts on their decision-making process.
