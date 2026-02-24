# heart-disease-risk-prediction
Random Forest model to predict heart disease risk using clinical features.
# eda (exploratory data analysis)
# these are the packages we will need
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
# removes need to download locally, this is our dataset
url = "https://archive.ics.uci.edu/ml/machine-learning-databases/heart-disease/processed.cleveland.data"
# file lacks column names, but there are the ones specified on source site corresponding to each column
column_names = [
    'age', 'sex', 'cp', 'trestbps', 'chol', 'fbs', 'restecg',
    'thalach', 'exang', 'oldpeak', 'slope', 'ca', 'thal', 'target'
]
# read in dataset with provided column names, specify that missing values are the '?' values
df = pd.read_csv(url, names=column_names, na_values="?")
# convert all numbers 1 to 4 into 1, leave 0's as 0 to become binary absence or presence of heart disease
df['target'] = df['target'].apply(lambda x: 1 if x > 0 else 0)
df.head()
# get broad overview of data - how many missing values, data type of column
df.info()
# replace missing values with median of the column
df[['ca', 'thal']] = df[['ca', 'thal']].fillna(df[['ca', 'thal']].median())
df.info()
df.describe()
# correlation heatmap to show why these features were chosen for analysis
plt.figure(figsize=(12, 8))
sns.heatmap(df.corr(), annot=True, cmap='coolwarm', fmt='.2f')
plt.title("Correlation Between All Features", fontsize=14)
plt.tight_layout()
plt.show()
# counts - check proportion of target values
sns.countplot(data=df, x='target')
plt.title('Distribution of heart disease')
plt.xticks([0, 1], ['Absent', 'Present'])
plt.show()
# use random forest for training
# !pip show pandas
# !pip show sci
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import classification_report
# separate features from target
# create matrix with just features to be used for prediction and leave out
# target, axis = 1 specifies variable to be dropped was a column
X = df.drop("target", axis=1)
# create vector for just the target variable
y = df["target"]
# split data: 20 percent for testing and 80 percent for learning
X_train, X_test, y_train, y_test = train_test_split(
    X, y,
    test_size=0.2,
    random_state=42
)
# number of samples in the training data
num_samples = X_train.shape[0]
# calculate good estimate for value to use for max_depth
max_depth_value = int(np.log2(num_samples))
# create random forest model
rf = RandomForestClassifier(
    n_estimators=100, max_depth= max_depth_value, random_state=42,
)
# train random forest
rf.fit(X_train, y_train)
# make predictions on the testing data
y_pred = rf.predict(X_test)
# print report
print(classification_report(y_test, y_pred))
