# Employee-Turnover-Rate-Prediction
Employee turnover refers to the total number of employees who leave a company over a certain time period. It includes those who exit voluntarily as well as employees who are fired or laid off—that is, involuntary turnover. High turnover can be costly and disruptive to a business, so it's important to understand what causes it and how to reduce it.

This project aims to build a Machine Learning model to analyze various factors that contribute to Employee Turnover including job satisfaction, last evaluation, number of projects, average monthly hours, time spent in company, accidents at workplace, promotion in 5 years, department and salary.

Here the variable 'Left' is used to indicate whether an employee stay or leave an organization.

# Steps performed to build the model:-

__Step 1 – Data Exploration__
1)	Import Employees dataset and check for null values.
2)	Checked datatype of all columns to know how many numeric and categorical columns are present in dataset.

__Univariate Analysis :-__
1)	Found unique values for each column and plotted frequency distribution plot for column with continuous data.
2)	The inferences from each plot is written in source code file.
          
 __Bivariate Analysis :-__
1)	Plotted Kdeplot and countplots for various columns with ‘left’ column as hue in order to visualize effect of ‘left’ column data on respective columns.

  __Multivariate Analysis :-__
1)	Plotted heat map for all numerical columns.
2)	Extracted the column depicting correlation of other columns with left column.
3)	 Found features having high correlation with left column.

__Step 2 – Performed clustering of Employees using K means__
1)	Separated rows which contain data of only those employees who left the Organization.
2)	Scaled the data using Standard Scaler so model learns better.
3)	Applied ‘Elbow Method’ to find optimal number of clusters.
4)	Again, applied K means with optimal number of cluster and segregated employees in three groups.
5)	Wrote inferences about each cluster in source code file.

__Step 3 – Data preparation for Classification Model Building__
1)	Checked for the class imbalance in the Target variable ‘left’.
2)	Separated columns containing numeric and categorical data with help of ‘select_dtype’ function.
3)	Converted the categorical variables into numerical variables using dummies function in Pandas.
4)	Merged both data frames to form one final dataset.

__Step 4 – Training Logistics Regression model without applying SMOTE technique.__
1)	Separated feature and target variable.
2)	Done stratified split of dataset in 80:20 ratio of training and testing with random state 123.
3)	Imported and trained the Logistic model on train data.
4)	Calculated accuracy score, confusion matrix and printed classification report to see performance of model.
5)	The model accuracy comes out to be very low.
6)	Applied SMOTE technique on dataset to cure class imbalance.
7)	Again trained the model.
8)	This time the accuracy has improved a bit.
9)	Obtained the coefficient of features from trained model to find their contribution in classification and plotted them for visual representation.

__Step 5 – Training Random Forest model__
1)	Imported Random Forest algorithm and fitted training data.
2)	There comes out to me sharp increase in model accuracy with increased Recall and precision.

__Step 6 – Training XG Boost model__
1)	Imported XG Boost algorithm and fitted training data.
2)	The accuracy of the model has increased slightly with increased Recall and precision.

__Step 7 – Comparing performance of all models__
1)	Plotted ROC-AOC curve for all four models (Logistics without SMOTE, Logistics with Smote, Random forest and XG Boost.
2)	Found XG Boost perform best among all models.
3)	Applied K – Fold Technique on all models.
4)	Found XG Boost perform best among all models here also.
5)	
__Step 8 – Segregating Employees according to risk associated with them__
1)	Chose XG Boost as final model to train our data and obtained probability score/value for all the employees.
2)	Add separate column named probability in original dataset.
3)	On the basis of probability score separated employees into 4 Zones namely Safe Zone, Low Risk Zone, Medium Risk Zone, High Risk Zone.
4)	Found model has predicted High Risk employees with 99.45% accuracy.
5)	Plotted Countplot of various zone employees.


__Gave Employee Retention Strategies based on findings from analysis of the Data.__

# Tools and Technologies used
1) __Language__ : Python
2) __IDE__ : Jupyter Notebook
3) __Pandas__ : For loading the dataset and performing data wrangling
4) __Matplotlib__: For data visualization.
5) __Seaborn__: For data visualization.
5) __NumPy__: For some math operations in predictions.
6) __Sklearn__: For the purpose of analysis,prediction and evaluation
7) __Method__: User Based Collaborative Filtering and Item based Collaborative Filtering

