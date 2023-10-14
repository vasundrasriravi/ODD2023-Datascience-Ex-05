# Ex:05 Feature Generation
# AIM:
To read the given data and perform Feature Generation process and save the data to a file.
# EXPLANATION:
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
# ALGORITHM:
## STEP 1:
Read the given Data.
## STEP 2:
Clean the Data Set using Data Cleaning Process.
## STEP 3:
Apply Feature Generation techniques to all the feature of the data set.
## STEP 4:
Save the data to the file.
# PROGRAM:
```
Developed by: VASUNDRA SRI R
Register no: 212222230168
```
## Encoding.csv file:
```
import pandas as pd
df=pd.read_csv('/content/Encoding Data.csv')
df.head()
df['ord_2'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot']
en= OrdinalEncoder(categories = [climate])
df['ord_2']=en.fit_transform(df[["ord_2"]])
df
le = LabelEncoder()
df['Nom_0'] = le.fit_transform(df[["nom_0"]])
df
!pip install --upgrade category_encoders
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(df['bin_1'])
df  = pd.concat([df,data],axis=1)
df
be = BinaryEncoder()
data = be.fit_transform(df['bin_2'])
df  = pd.concat([df,data],axis=1)
df
```
## Data.csv:
```
import pandas as pd
df1 = pd.read_csv("/content/data.csv")
df1.head()
df1['Ord_1'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot','Very Hot']
en= OrdinalEncoder(categories = [climate])
df1['Ord_1']=en.fit_transform(df1[["Ord_1"]])
df1
df1['Ord_2'].unique()
cl = ['High School','Diploma','Bachelors','Masters','PhD']
en= OrdinalEncoder(categories = [cl])
df1['Ord_2']=en.fit_transform(df1[["Ord_2"]])
df1
le = LabelEncoder()
df1['City'] = le.fit_transform(df1[["City"]])
df1
from category_encoders import BinaryEncoder
be = BinaryEncoder()
dat = be.fit_transform(df1['bin_1'])
df1  = pd.concat([df1,dat],axis=1)
df1
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data1 = be.fit_transform(df1['bin_2'])
df1  = pd.concat([df1,data1],axis=1)
df1
```
## BMI.csv file:
```
import pandas as pd
df2 = pd.read_csv("/content/bmi.csv")
df2.head()
be = BinaryEncoder()
data2 = be.fit_transform(df2['Gender'])
df2  = pd.concat([df2,data2],axis=1)
df2
df2 = pd.get_dummies(df2, prefix=['Index'] ,columns=['Index'])
df2
```
# OUTPUT:
## Encoding.csv file:
### Initial data:
![ed](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/9975de99-1cf8-406e-869b-f3eb8604156c)

### Unique Value:
![ed1](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/7c923704-c004-4df1-9a56-e185c88b6e58)

### Ordinal Encoder:
![ed2](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/0cac78d1-99ce-4330-9329-dc6a3df3a01d)

### Label Encoder:
![ed3](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/82219fea-0e43-4f84-b81d-39afe9cb4d17)

### Binary Encoder:
![ed4](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/9fe7a0d9-f123-4029-a864-c71d8ad17d42)
![ed5](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/dbd70748-c9eb-48de-8a6a-7f029fd95e9c)

## Data.csv file:
### Initial data:
![da1](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/c4239c6e-9e0d-4430-8969-7f4aa0486c55)

### Unique data:
![da2](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/ff04655f-72f4-4fe3-8942-446071319d52)

### Ordinal Encoder:
![da3](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/0d3237bb-1b19-4411-a435-ca81c889034a)
![da4](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/49544d30-25f1-4ea3-8ce3-7e8c96bd306a)

### Label Encoder:
![da5](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/7957c39c-e506-4c6e-89de-f2c4eb18997f)

### Binary Encoder:
![da6](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/7732dcd1-5bb3-4da3-b23f-783f29b131ab)
![da7](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/ff8f9a75-aacb-4e12-b58a-5c967f8dd87d)

## bmi.csv file:
### Initial data:
![b1](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/3919f499-0f83-4534-bf47-7928e9b700df)

### Binary Encoders:
![b2](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/7537668e-6e76-44fb-87f3-2dee29d3b85c)

### Dummies:
![b3](https://github.com/vasundrasriravi/ODD2023-Datascience-Ex-05/assets/119393983/9e19a097-5c78-4146-ad37-a49a7814ee8c)

# RESULT:
The Feature Generation process was performed and saved the data to a file.
