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
        df = pd.read_csv("/content/titanic_dataset.csv")
        df 
  <img width="1293" height="465" alt="Screenshot 2026-08-02 191459" src="https://github.com/user-attachments/assets/3f1bcd78-97b1-4232-aa4f-eb424deb7f1f" />
      
        df.info()
 <img width="441" height="386" alt="Screenshot 2026-08-02 191449" src="https://github.com/user-attachments/assets/04646a01-b644-440d-8eb6-b33d248fcda1" />
       
        df.dtypes
<img width="230" height="516" alt="Screenshot 2026-08-02 191437" src="https://github.com/user-attachments/assets/06edd3b8-60f1-4261-8132-1e9b57b4a6bc" />
        
        df.describe()
 <img width="852" height="340" alt="Screenshot 2026-08-02 191422" src="https://github.com/user-attachments/assets/278a56c1-e8b0-4a17-9da7-05dc17386fbf" />
    
        df["Survived"].value_counts()
<img width="170" height="188" alt="Screenshot 2026-08-02 191416" src="https://github.com/user-attachments/assets/3f715d37-f394-40ac-a51d-b5011b4ed91a" />
        
        df.nunique()
 <img width="193" height="500" alt="Screenshot 2026-08-02 191408" src="https://github.com/user-attachments/assets/844f885a-4e31-4532-9b9b-fb90eb29ead8" />
       
        import seaborn as sns
        sns.countplot(data=df,x="Survived")
<img width="652" height="515" alt="Screenshot 2026-08-02 191358" src="https://github.com/user-attachments/assets/e69fb6d4-3b64-4b45-9d20-73b9854cb164" />
        
        sns.boxplot(data=df,x="Age")
<img width="600" height="515" alt="Screenshot 2026-08-02 191345" src="https://github.com/user-attachments/assets/59dff50f-1d14-4017-93eb-7c4db1604c0e" />
        
        sns.histplot(data=df,x="Age")
<img width="667" height="516" alt="Screenshot 2026-08-02 191337" src="https://github.com/user-attachments/assets/944d8d52-ad95-44ec-81a3-7e7ced07b69c" />
        
        df.rename(columns={'Sex':'Gender'},inplace=True)
        df
 <img width="1291" height="462" alt="Screenshot 2026-08-02 191328" src="https://github.com/user-attachments/assets/c1bca2f5-f97e-40f7-8336-178fdf8a827a" />
       
        sns.catplot(x="Survived",hue="Gender",data=df,kind='count')
<img width="666" height="582" alt="Screenshot 2026-08-02 191318" src="https://github.com/user-attachments/assets/17c43db8-cc08-4ced-8044-36ede4bbc71d" />
        
        df.boxplot(column="Age",by="Survived")
 <img width="655" height="542" alt="Screenshot 2026-08-02 191310" src="https://github.com/user-attachments/assets/a754ba24-dfc4-4c66-a555-92517fcf571a" />
       
        sns.scatterplot(x=df["Age"],y=df["Fare"])
<img width="652" height="518" alt="Screenshot 2026-08-02 191302" src="https://github.com/user-attachments/assets/d4ede541-53ee-4055-8353-4c32d4f4b3dc" />
      
        sns.barplot(x=df["Survived"],y=df["Fare"])
<img width="647" height="521" alt="Screenshot 2026-08-02 191253" src="https://github.com/user-attachments/assets/55e85fa9-dfaf-401b-b095-eb05d426173a" />
        
        sns.boxplot(x="Pclass",y="Age",hue="Gender",data=df)
<img width="652" height="512" alt="Screenshot 2026-08-02 191245" src="https://github.com/user-attachments/assets/678c80b2-8631-4a0f-aee6-aaa9fe8149df" />
        
        sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
 <img width="1193" height="582" alt="Screenshot 2026-08-02 191236" src="https://github.com/user-attachments/assets/2a3091f0-21ae-4db0-9a71-461f6117a462" />
       
        sns.heatmap(df.corr(numeric_only=True),annot=True)
<img width="836" height="640" alt="Screenshot 2026-08-02 191040" src="https://github.com/user-attachments/assets/cc9a2736-17a8-468d-a7ff-11d72c843a8d" />


        
# RESULT
        We have performed Exploratory Data Analysis on the given data set successfully.
