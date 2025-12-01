# Estimation of Obesity Level Based on Lifestyle and Eating Habits

## Data source
url = "https://raw.githubusercontent.com/RohitG57/Estimation-of-obesity-levels-based-on-eating-habits-and-physical-condition/main/ObesityDataSet_raw_and_data_sinthetic.csv"

### 1. Abstract: 
This study investigates how lifestyle habits, eating behaviors, and physical conditions relate to 
obesity levels using the UCI Obesity Dataset. Statistical analysis, including t-tests, Chi-square 
tests, and ANOVA, identified significant differences across groups, such as higher average 
weights in males, greater weight among individuals with a family history of overweight, and 
strong impacts of snacking frequency on weight. A binary logistic regression model further 
revealed that BMI is the strongest predictors of obesity, while lifestyle factors such as water 
intake, exercise frequency, and meal patterns contribute smaller but meaningful effects. Overall, 
the findings show that physical measures are the primary determinants of obesity, with lifestyle 
behaviors providing supportive insights. This analysis emphasizes the value of data-driven 
approaches for improving obesity assessment and risk prediction. 

### 2. Introduction: 
Obesity is a growing global health concern linked to lifestyle habits, physical activity, and 
genetics. Understanding the factors that contribute to obesity is essential for prevention and 
early intervention. This project uses the “Estimation of Obesity Levels Based on Eating Habits 
and Physical Condition” dataset from the UCI Machine Learning Repository, which includes 
information on eating patterns, physical activity, and demographic factors of individuals from 
Mexico, Peru, and Colombia. The goal is to analyze the relationship between lifestyle behaviors 
and obesity levels and to develop predictive models that classify individuals’ obesity risk. The 
study highlights key factors influencing obesity and provides insights for data-driven health 
interventions. 

#### 2.1 Data Source and Scope: 
The dataset used in this project comes from the UCI Machine Learning Repository, specifically 
the file ObesityDataSet_raw_and_data_sinthetic.csv (UCI Obesity Dataset). It contains 2,111 
records of individuals from Mexico, Peru, and Colombia, with 17 attributes covering 
demographics, eating habits, physical activity, and family history related to being overweight. 
The unit of analysis is an individual person, with each row representing a unique participant. 

### The dataset includes: 
● Demographics: Gender, Age, Height, Weight, Family history of overweight. 

● Eating habits: HighCalFreq, VegMealFreq, MealsPerDay, Snacking, WaterIntake, 
TrackCalories. 

● Lifestyle habits: ExerciseFreq, ScreenTime, AlcoholFreq, SMOKE, TransportMode. 

● Target variable: ObesityLevel, classified into “Insufficient Weight,” “Normal Weight,” 
“Overweight Level I & II,” and “Obesity Type I–III.” 

Notably, 77% of the data was generated synthetically using the Weka tool and SMOTE 
filter, while 23% was collected directly from users through a web platform. This 
combination ensures a robust dataset for analysis while maintaining representation of real-world 
behavior. 

This project focuses on analyzing relationships between lifestyle habits and obesity using 
hypothesis testing and regression analysis, providing insights into key factors influencing 
obesity risk.  

### 3. Data Acquisition and Cleaning/Preprocessing : 

#### 3.1 Data Acquisition and Initial Load : 
The dataset used in this project was obtained from the UCI Machine Learning Repository. 
Specifically, the file ObesityDataSet_raw_and_data_sinthetic.csv was downloaded in CSV 
format. 
For the analysis, Python libraries such as pandas, numpy, matplotlib, and seaborn were used. 
The dataset was loaded into a Pandas DataFrame directly from the GitHub repository: 

url = 
"https://raw.githubusercontent.com/RohitG57/Estimation-of-obesity-levels-based-on-eating-habits-and-physical-condition/main/ObesityDataSet_raw_and_data_sinthetic.csv" 
df= pd.read_csv(url) 

The dataset was loaded into a Pandas DataFrame for inspection and further analysis using 
pd.read_csv().  

#### 3.2 Data Cleaning and Preprocessing:  
Step 1. Renaming Columns: The original dataset contained long and complex column names. 
To simplify analysis and avoid syntax issues in Python, the columns were renamed with shorter, 
standardized names. 

Step 2. Converting Columns to Appropriate Data Types: To optimize memory usage and 
improve performance, we converted certain columns to more suitable data types. 

● Categorical Conversion - Columns with repeated text values, such as Gender, Snacking, 
AlcoholFreq, TransportMode, ObesityLevel, were converted to the category data type. This 
reduces memory usage and improves performance when analyzing repeated text values.  

Step 3. Checking for missing value : The dataset was checked for missing or invalid values. 
No missing values were found, so no imputation or cleaning was necessary for this step. 

Step 4. Checking for Duplicate Records : The dataset was checked for duplicate rows, and a 
few duplicate observations were found. These duplicates were removed to ensure data 
accuracy and prevent repeated information from affecting the analysis. The final dataset 
contained 2,087 rows and 17 columns, ensuring cleaner and more reliable data for analysis. 

Renaming some columns' names:

df.rename(columns={
    "family_history_with_overweight": "FamilyOverweight",
    "FAVC": "HighCalFreq",
    "FCVC": "VegMealFreq",
    "NCP": "MealsPerDay",
    "CAEC": "Snacking",
    "CH2O": "WaterIntake",
    "SCC": "TrackCalories",
    "FAF": "ExerciseFreq",
    "TUE": "ScreenTime",
    "CALC": "AlcoholFreq",
    "MTRANS": "TransportMode",
    "NObeyesdad": "ObesityLevel"
}, inplace=True)



