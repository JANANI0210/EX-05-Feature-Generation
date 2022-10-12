# EX-05-Feature-Generation


## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# CODE

### Data

1.

import pandas as pd

import seaborn as sns

df=pd.read_csv("/content/data.csv")

df.info()

2.

df.isnull().sum()

3.

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df['Ord_2'] = le.fit_transform(df['Ord_2'])

sns.set(style ="darkgrid")

sns.countplot(df['Ord_2'])

4.

from sklearn.preprocessing import OneHotEncoder

enc = OneHotEncoder()

enc = enc.fit_transform(df[['City']]).toarray()

encoded_colm = pd.DataFrame(enc)

df = pd.concat([df, encoded_colm], axis=1)

df = df.drop(['City'], axis=1)

df.head(10)

5.

df = pd.get_dummies(df, prefix=['Ord_2'], columns=['Ord_2'])

df.head(10)

6.

df = pd.get_dummies(df, prefix=['Ord_1'], columns=['Ord_1'])

df.head(10)

### Encoding Data

1.

import pandas as pd

import seaborn as sns

df=pd.read_csv("/content/Encoding Data.csv")

df.info()

2.

df.isnull().sum()

3.

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df['ord_2'] = le.fit_transform(df['ord_2'])

sns.set(style ="darkgrid")

sns.countplot(df['ord_2'])

4.

from sklearn.preprocessing import OneHotEncoder

enc = OneHotEncoder()

enc = enc.fit_transform(df[['nom_0']]).toarray()

encoded_colm = pd.DataFrame(enc)

df = pd.concat([df, encoded_colm], axis=1)

df = df.drop(['nom_0'], axis=1)

df.head(10)

5.

df = pd.get_dummies(df, prefix=['bin_2'], columns=['bin_2'])

df.head(10)

### titanic_dataset

1.

import pandas as pd

df=pd.read_csv("/content/titanic_dataset.csv")

df.info()

2.

df.isnull().sum()

3.

df['Age']=df['Age'].fillna(df['Age'].mean())

df['Cabin']=df['Cabin'].fillna(df['Cabin'].mode()[0])

df['Embarked']=df['Embarked'].fillna(df['Embarked'].mode()[0])

df.isnull().sum()

4.

from sklearn. preprocessing import LabelEncoder

le = LabelEncoder()

df ['Sex'] = le.fit_transform(df['Sex' ])

sns . set(style ="darkgrid")

sns . countplot (df [ 'Sex' ])

5.

from sklearn. preprocessing import OneHotEncoder

enc = OneHotEncoder ( )

enc = enc. fit_transform(df [ [ 'Name' ]]) . toarray()

encoded_colm = pd. DataFrame(enc)

df = pd. concat([df, encoded_colm], axis=1)

df = df . drop(['Name' ], axis=1)

df . head(10)

6.

df = pd.get_dummies (df, prefix=['Ticket'], columns=[ 'Ticket'])

df . head ( 10 )

7.

df = pd.get_dummies (df, prefix=['Embarked'], columns=[ 'Embarked'])

df . head ( 10 )

8.

df= pd.get_dummies(df, prefix=['Cabin'], columns=[ 'Cabin' ])

df . head (10)


# OUPUT
