# Ex:05 Feature Generation
### AIM :
To read the given data and perform Feature Generation process and save the data to a file.

### EXPLANATION :

Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

### ALGORITHM :


### STEP 1 :
Read the given Data

### STEP 2 :
Clean the Data Set using Data Cleaning Process

### STEP 3 :
Apply Feature Generation techniques to all the feature of the data set

### STEP 4 :
Save the data to the file

### PROGRAM :
```
NAME :HARINI V
REG NO : 212222230044

```

### Encoding.csv :

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
### OUTPUT :
For encoding.csv file:

![274237486-6c34ae2c-4d52-456d-bb59-9b7f5cc8f3fe](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/db0bf84b-d1d2-4bbb-af0d-cc7182e4a368)

![274237547-21345ca8-6a5e-4d97-8915-5768d2a2b1ff](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/5e4279e4-3309-4013-8607-3fed068c8447)


![274237584-c0a9c907-2093-4843-9cf0-90733db72cdd](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/42184ca9-8ddb-4cf0-85c2-ece4bae32945)

![274237606-4256251a-0674-4582-a620-a496043a3901](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/d1e0d943-caf6-45c0-8cca-b865282ffe9d)


![274237626-845df31e-9fcb-4875-a1e7-3ac70619dc37](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/33706f4d-933d-4867-ac7a-5e90e95de375)


![274237690-d2e22be5-704d-49c7-bb93-68500443d07a](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/823b6ec5-e8c7-46c3-a0a0-4171a6dfa3f8)


### Data.csv :

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

### OUTPUT :

For Data.csv file:

![274237802-c0cf7a08-e44a-43f1-b950-535934cbe5d6](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/f25bfbc9-7e4e-4846-898f-85e69c19b5b0)
![274237827-1e68c3e1-d24f-45c1-a2cd-064faf4bfb2d](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/cc5742bf-36ef-4561-ba23-c8960c0bf418)
![274237844-a299b218-7585-4b86-a770-a432c7d7e6f6](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/efa22e92-f11d-428a-92f6-3def929f8473)


![274237857-0bf8837c-21dd-4b8f-a46c-385e8bf736a7](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/febf5e94-6f8f-42a8-97f7-87b35b1424ea)

![274237873-84ada579-4192-4bac-9878-821db5289436](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/818f29dc-3049-4579-aa53-b4e670ac3c25)

![274238817-d2897922-ec3d-4940-bf0a-0e8bc043d787](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/a11b5a21-ddbf-4131-b82a-061348df0a3c)


![274237893-6f0d391e-3702-40b5-9a37-03eb5eae2565](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/91ad2490-92db-4a14-9e6f-2b17f6312b92)

### BMI.csv file:
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
### OUTPUT :

For bmi.csv file:


![274237927-76f9810f-3172-4b60-bdc1-50d44d22333b](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/51f671c1-c466-41db-a2d9-6e9dc9617431)


![274237936-dd491703-47c8-45f0-86a3-c56c9bd8cc1a](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/3817d8db-da9c-4c4c-8b7a-bdb2699070ba)

![274237947-2c20cca9-b38d-49cc-8e40-47a73e727506](https://github.com/Aravindsamy04/ODD2023-Datascience-Ex-05/assets/113497037/e8405041-1b45-4cea-9abc-d791b4a3cdf8)




### RESULT:
The Feature Generation process was performed and saved the data to a file.

























