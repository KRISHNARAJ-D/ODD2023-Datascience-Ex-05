# Ex:05 Feature Generation
# AIM:
To read the given data and perform Feature Generation process and save the data to a file.

# Explanation:
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

# ALGORITHM
## STEP 1
Read the given Data
## STEP 2
Clean the Data Set using Data Cleaning Process
## STEP 3
Apply Feature Generation techniques to all the feature of the data set
## STEP 4
Save the data to the file

# Program:
```
Developed by: KRISHNARAJ D
Register number: 212222230070
```
## For Encoding.csv file:
```
import pandas as pd
df=pd.read_csv('Encoding Data.csv')
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
df1 = pd.read_csv("data.csv")
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
## For Encoding.csv
## Initial value
![275247920-c333e662-9fa2-4db9-ac40-e4b7b8b31fdd](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/537e2659-ec6e-4267-8527-86125ebfe1c3)


## Unique value:
![275247962-f2438e74-4b75-4855-844c-6f4f488ee284](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/ab2db6e5-fed5-46b4-97da-a22a337045e4)


## Ordinal encoder:
![275248068-d21611f0-20bf-4dda-82fc-a32b4fb0087a](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/a0234875-1f45-40e4-bc94-8c9bd57ce299)


## Label encoder:

![275248098-5713beec-77d0-485c-a8d2-e9f0a1058921](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/6ed74b02-fbe1-4514-8787-1dffe36c7725)

## Binary encoder:
![275248134-39437da8-daa7-4c4b-9699-f3c1f473fec8](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/3da5ee15-835a-48ba-92ae-09a7fc7254e9)

![275248176-2cc04408-5de4-4440-a435-050f5aac70a5](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/1563c072-a66c-4a25-857a-2ab99647e994)

## For Data.csv file:
## Initial data:

![275303834-2083700f-cd00-448e-8582-50b791b492d5](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/c2dd82c4-bba2-44c0-8bf7-bd78305af294)

## Ordinal encoder:
![275303883-c009a540-26ba-4f99-a745-40e9457bd92a](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/cb9f1462-38c3-48ee-8c95-28c1b05a43bc)

![275303899-7e55c1b4-00db-4160-ac47-4b16f12f2fa9](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/7d8c033a-5601-4da3-b378-793704fee7a0)



## Label encoder:
![275303934-41b5f0cc-8d2a-4bfb-866f-ab4c74d6f077](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/eaff7acb-aa19-4cab-882b-eaaaca063077)


## Binary encoder:
![275303956-48384b43-a12c-4ef4-a22b-f1e693db3c3c](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/c2365753-60be-4a34-9ed8-a0b6f5ccca8a)

![275303980-06c85884-d4a5-40fa-9b87-9f32a2600c8f](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/7e7996fe-f0bb-4b12-9992-df58165dac99)

## For BMI.csv file:
## Initial data:
![275304023-f01f3917-7111-4d65-90d4-cc9836943c33](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/b5a1e418-e3f3-4d45-aaed-74538d762204)


## Binary encoders:
![275304178-138a1f1e-ddcb-4cd5-9d9b-147a2363a12b](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/17c6f87b-282f-40eb-8214-7473d251d8f4)


## Dummies:
![275304253-36fce9c1-0b99-4f99-aab8-0eb8cb935181](https://github.com/KRISHNARAJ-D/ODD2023-Datascience-Ex-05/assets/119559695/9e8cd427-90b4-4a2f-8a11-aff3a89f43a9)


# RESULT:
The Feature Generation process was performed and saved the data to a file.
