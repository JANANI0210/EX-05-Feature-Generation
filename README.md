# EX-05-Feature-Generation                                                                                          
                                                                                                                     MONICA DK 212220040092


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

![Screenshot (182)](https://user-images.githubusercontent.com/86832944/195375830-7be07d72-d9cd-4b23-95ff-6d3e9ed7da57.png)

![Screenshot (183)](https://user-images.githubusercontent.com/86832944/195375903-ff27ae09-c3da-4728-bbb8-d06c4fde3c6e.png)

![Screenshot (184)](https://user-images.githubusercontent.com/86832944/195376051-589728ca-7c56-4929-ad21-22dba31fd545.png)

![Screenshot (185)](https://user-images.githubusercontent.com/86832944/195376155-04f5c1b0-1cf4-4cc6-aecd-eeef991b73cf.png)

![Screenshot (187)](https://user-images.githubusercontent.com/86832944/195376332-74246623-ec2a-4bf6-96e4-3645a890a4de.png)

![Screenshot (188)](https://user-images.githubusercontent.com/86832944/195377228-5262be14-7e51-40a8-854f-806bc50b453d.png)

![Screenshot (189)](https://user-images.githubusercontent.com/86832944/195377286-44bfc656-6105-413d-8a6d-e84058d66a89.png)

![Screenshot (190)](https://user-images.githubusercontent.com/86832944/195377690-32999d29-1d6d-41cc-b672-31abdaab2248.png)

![Screenshot (191)](https://user-images.githubusercontent.com/86832944/195377802-29ecbeb9-cbc9-4aa8-bec0-326257b52b65.png)

![Screenshot (192)](https://user-images.githubusercontent.com/86832944/195378033-1a9692d2-e8a4-451d-8eb9-a531ad5a3d7e.png)

![Screenshot (193)](https://user-images.githubusercontent.com/86832944/195378100-a7468ff9-91cf-4b0c-9401-20376ac887b2.png)

![Screenshot (194)](https://user-images.githubusercontent.com/86832944/195378273-655db42f-c575-4811-9102-10e5600df26d.png)

![Screenshot (195)](https://user-images.githubusercontent.com/86832944/195378314-d4d1c575-c0e9-4a65-8cb0-c9b457d20b22.png)

![Screenshot (197)](https://user-images.githubusercontent.com/86832944/195378375-8e0c43ee-22da-403f-b539-a4e452d45c87.png)

### RESULT:

Thus, the given data is read and Feature Generation process is performed and saved the data to a file. 




