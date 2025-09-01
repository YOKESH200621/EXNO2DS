# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
                import pandas as pd
                import seaborn as sns

                df=pd.read_csv("titanic_dataset.csv")
                df
                
<img width="1199" height="469" alt="Screenshot 2025-08-29 151240" src="https://github.com/user-attachments/assets/417e128f-641c-4e20-a40d-5fb720de14a5" />

        df.shape
        df.info()
        df.describe()

<img width="1082" height="503" alt="Screenshot 2025-08-29 151356" src="https://github.com/user-attachments/assets/7d84542d-fcbf-47d0-aac4-90310176e54e" />

<img width="961" height="416" alt="Screenshot 2025-08-29 151431" src="https://github.com/user-attachments/assets/baec6c82-da81-4e40-80c5-ff77724818a6" />

        df.set_index("PassengerId",inplace=True)
        df

<img width="1151" height="483" alt="Screenshot 2025-08-29 151505" src="https://github.com/user-attachments/assets/f53773a3-9379-4cd3-96b8-7ca44c59f23e" />

        df.isnull()

<img width="1144" height="597" alt="Screenshot 2025-08-29 151548" src="https://github.com/user-attachments/assets/c2740bbf-fc26-4428-a1e0-8d09d479bc9f" />

        print(df.isnull().sum())
        df.nunique()

<img width="918" height="417" alt="Screenshot 2025-08-29 151620" src="https://github.com/user-attachments/assets/1346ba83-8060-4bf0-9f87-8d48923cbaab" />

        #total values
        df['Survived'].value_counts()

<img width="780" height="152" alt="Screenshot 2025-08-29 151655" src="https://github.com/user-attachments/assets/34ec2265-64aa-453f-b91a-d098bae78762" />

        #unique values in that column
        df.Survived.unique()

<img width="769" height="58" alt="Screenshot 2025-08-29 151721" src="https://github.com/user-attachments/assets/1e1cb96e-9b03-42d0-ae0d-4269e6db6d33" />

        #univariate analysis
        #grouping based on sex
        sns.countplot(x="Survived",hue='Sex',data=df)

<img width="934" height="535" alt="Screenshot 2025-08-29 151749" src="https://github.com/user-attachments/assets/fe65ecf3-94fd-4fd1-a481-a5a749b4753f" />

        df.rename(columns={'Sex':'Gender'},inplace=True)
        df
        
<img width="1226" height="500" alt="Screenshot 2025-08-29 151827" src="https://github.com/user-attachments/assets/3ed94a69-057d-44ac-a5e4-8b84f80db944" />

        sns.countplot(x="Gender",hue='Pclass',data=df)

<img width="1137" height="624" alt="Screenshot 2025-08-29 151902" src="https://github.com/user-attachments/assets/1221be66-f8c5-497c-938d-e170afeb4460" />

        sns.catplot(x="Survived",hue="Gender",data=df,kind='violin')

<img width="1280" height="827" alt="Screenshot 2025-08-29 151943" src="https://github.com/user-attachments/assets/05d0d693-0bb1-43eb-82a6-3b63c85ae0b1" />

        sns.catplot(x="Survived",hue="Gender",data=df,kind='count')

<img width="1255" height="820" alt="Screenshot 2025-08-29 152031" src="https://github.com/user-attachments/assets/310fec6f-c730-4016-90db-7f4934a0de20" />

        sns.catplot(x="Survived",col="Gender",data=df,kind='count')

<img width="1242" height="612" alt="Screenshot 2025-08-29 152105" src="https://github.com/user-attachments/assets/d4350875-c145-4f3e-8f99-4873128b7fb8" />

        sns.boxplot(data=df)

<img width="1145" height="684" alt="Screenshot 2025-08-29 152139" src="https://github.com/user-attachments/assets/eed2c06a-8e57-45b4-b077-3e6046ef1e64" />

        df.boxplot(column='Age',by='Pclass')


<img width="1057" height="625" alt="Screenshot 2025-08-29 152211" src="https://github.com/user-attachments/assets/89c488ba-05d5-4938-a0d4-8d71edd60f6d" />

        sns.scatterplot(x='Age',y='Fare',data=df)

<img width="1170" height="648" alt="Screenshot 2025-08-29 152241" src="https://github.com/user-attachments/assets/a0f24154-2d38-4abe-bd2f-e70fcc790851" />

        sns.jointplot(x='Age',y='Fare',data=df)


<img width="1136" height="814" alt="Screenshot 2025-08-29 152314" src="https://github.com/user-attachments/assets/f3d468f8-af14-4407-bdc5-7d4f08ff4a9e" />

        sns.jointplot(x='Age',y='Fare',data=df,kind='kde')


<img width="1228" height="878" alt="Screenshot 2025-08-29 152348" src="https://github.com/user-attachments/assets/0cbd2c2b-8d4b-4288-8195-fba483526b49" />

        sns.jointplot(x='Age',y='Fare',data=df,kind='hist')



<img width="1074" height="877" alt="Screenshot 2025-08-29 152421" src="https://github.com/user-attachments/assets/e79f6772-579b-42f2-8c9c-df7129023594" />


        #pairwise relationship
        sns.pairplot(data=df)


<img width="1251" height="746" alt="Screenshot 2025-08-29 152454" src="https://github.com/user-attachments/assets/19897dba-a3b6-4785-92db-e3a8897cb91a" />

        #multivariate analysis
        cor1=df.select_dtypes(include=['number']).corr()
        sns.heatmap(cor1,annot=True)


<img width="1106" height="823" alt="Screenshot 2025-08-29 152525" src="https://github.com/user-attachments/assets/6eb2ba63-21f2-477e-8771-83b8d947ee34" />

        group=df.groupby(['Pclass','Survived'])
        pclass_survived=group.size().unstack()
        sns.heatmap(pclass_survived,annot=True,fmt='d')


<img width="1057" height="772" alt="image" src="https://github.com/user-attachments/assets/367e5283-71d6-4b31-babf-1a46f80cf971" />



# RESULT
            Thus the given titanic dataset is analysed through exploratory data analysis.
