# 🎓 Student's Journey to Career Success Project | Python
![image](https://github.com/user-attachments/assets/bd7233e7-aeff-4e43-9534-9b0dd613268c)

Understanding the transition from **education to employment is essential for enhancing career readiness and closing skill gaps**. By mapping this journey, we can identify the academic factors, experiences, and skills that most significantly impact outcomes such as job offers, starting salaries, and career satisfaction. This knowledge enables educators, policymakers, and students to make informed decisions that **optimize educational strategies and career planning.**

## 📘 Project Overview 
This project dives into the journey from education to employment by analyzing **more than 5,000 student's profiles.** Using Python, it uncovers how academic performance, internships, projects, and learning styles shape career outcomes like job level and salary. The workflow includes data preprocessing, in-depth EDA, and rich visual storytelling through Seaborn and Matplotlib. By mapping out key trends and correlations, the project reveals the most influential factors in achieving career success offering valuable insights for students, educators, and decision-makers.

## 🎯 Key Objectives
- **Identify Key Influencers of Career Success** - Analyze how academic performance, internships, projects, and learning styles contribute to better job outcomes and salaries.
- **Bridge the Gap Between Education and Employment** - Uncover insights that can help students, educators, and institutions align learning paths with career opportunities.
- **Support Data-Driven Decision Making** - Provide actionable insights through statistical analysis and visualizations to guide career planning and educational improvements.
- **Highlight the Value of Practical Experience** - Examine the role of internships and hands-on projects in boosting employability and career readiness.
- **Create a Reusable Data Science Workflow** - Build a complete end-to-end data analysis pipeline with data cleaning, EDA, and visualization using Python.

## 📂 Data sources 
- Kaggle
<a href="https://github.com/Shakeel-Data/Student-Education-and-Career-Pathways-Python/blob/main/Student%20education%20and%20career%20.csv">csv</a>
- Python
<a href="https://github.com/shakeel-data/educational-and-career-outcomes-python/blob/main/Students_Education_%26_Career_Success.ipynb">codes</a>

## ⚙️ Project Workflow
### 1. Installing & Importing Libraries
Set up the environment by installing and importing key Python libraries such as Pandas, NumPy, Matplotlib, and Seaborn.

```python
# install numpy, pandas, seaborn, matplotlib

import numpy as np # linear algebra
import pandas as pd # data processing, CSV file I/O (e.g. pd.read_csv)
import seaborn as sns
import matplotlib.pyplot as plt
```

### 2. Loading & Understanding the Dataset
Imported the CSV file and reviewed basic structure, column names, and sample records to understand the data content.

```python
# Input data files are available in the read-only "../input/" directory
# For example, running this (by clicking run or pressing Shift+Enter) will list all files under the input directory
```

```python
from google.colab import files
uploaded = files.upload()
```
![image](https://github.com/user-attachments/assets/d710a87a-ab63-4f75-a31f-22361ca7e28d)


```python
# Load the dataset
df = pd.read_csv("Students education and career sucess.csv")

# Display first few rows
display(df.head())
```

![Display data](https://github.com/user-attachments/assets/dfddde34-a630-4880-90f6-c1b867a2a979)

### 3. Dataset Dimensions
Checked the number of rows and columns, and listed all column names along with their data types.

```python
rows,columns = df.shape
shp = pd.DataFrame({"": ["Rows", "Columns"], "Count": [rows, columns]})
shp.set_index("", inplace=True)
shp
```

### 4. Columns List and Datatypes
Knowing the data types early on is essential for selecting the right transformations, visualizations, and models later in the workflow.

```python
cols = pd.DataFrame({"Columns": df.columns})
cols = cols.reset_index(drop=True)
cols
```
![image](https://github.com/user-attachments/assets/cd893cd8-a5eb-4d08-9a62-583c94879f5c)

```python
df_summary = pd.DataFrame({
    "Column Name": df.columns,
    "Non-Null Count": df.count().values,  # Count of non-null values
    "Data Type": df.dtypes.values
})

df_summary
```
![image](https://github.com/user-attachments/assets/b7bf096e-c7ce-44cd-a09c-8a1591dc18c2)

### 5.🧹 Data Cleaning & Preprocessing
Verified and handled missing values, formatted columns, and prepared data for analysis using encoding techniques.

```python
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/e1953683-c2f6-4139-8e75-c5f8325bcf49)

### 6. Replacing Missing values
Missing value analysis confirms the dataset is clean.


### 7. 📊 Exploratory Data Analysis (EDA)
- Descriptive statistics and data visualizations offered deeper insights into the dataset.
- Key summary metrics-such as mean, median, and standard deviation-were used to understand central tendencies and variability.
- Additionally, visual tools like histograms, countplots, boxplots, and pairplots were employed to explore data distributions, identify outliers, and analyze relationships between variables.

```python
## Data visualization
plt.figure(figsize=(11,6))
sns.histplot(df['Starting_Salary'], bins=30, kde=True)
plt.title("Distribution of Starting Salaries")
plt.show()
```
![Salary distribution](https://github.com/user-attachments/assets/70332c22-3d07-47fb-b2ab-0d2e40a7a235)

### 📈 **Statistical information of Numerical Columns using Heat map**
Measures such as mean, median, minimum, maximum, standard deviation, and quartiles were computed to understand the central tendency and spread of each variable.

```python
df.describe()
```
![Statistical info](https://github.com/user-attachments/assets/c1a0fbaf-1c8e-4284-b466-fbd0d78617b4)

```python
plt.figure(figsize=(11, 6))
sns.heatmap(df.describe().T, annot=True, fmt=".2f", cmap="coolwarm", linewidths=0.5)
plt.title("Statistical Summary of Numerical Columns")
plt.show()
```
![image](https://github.com/user-attachments/assets/0d8435bf-aa39-4483-a8d5-febd090ab81f)

### 🔍 **Exploring Feature Relationships Using Pairplot**
- Pairplots were used to visually examine the relationships between multiple numerical features in the dataset.
- These plots display pairwise scatter plots alongside histograms, helping identify trends, clusters, and potential correlations.

```python
sns.pairplot(df[['University_GPA', 'Projects_Completed', 'Internships_Completed','Certifications', 'Job_Offers']])
plt.show()
```

![image](https://github.com/user-attachments/assets/fa0377cd-cae0-4a85-b17c-7c1b041dc66f)

### 📚 **Distribution of Field of Study**
- The distribution of the Field of Study variable highlights the number of students pursuing each academic discipline.
- Visualizing this distribution helps identify the most and least popular fields, providing insight into student preferences and academic trends.

```python
plt.figure(figsize=(11,6))
sns.countplot(x=df['Field_of_Study'])
plt.xticks(rotation=90)
plt.title("Distribution of Fields of Study")
plt.show()
```

![image](https://github.com/user-attachments/assets/10a6720b-9f18-4893-b34d-d8a1ae001500)

### 📦 Boxplot to check for outliers
- Boxplots were used to identify outliers and understand the spread of numerical features such as GPA, Starting Salary and internship.
- These plots display the median, quartiles, and potential outliers beyond the whiskers, making it easy to detect unusually high or low values. Identifying outliers is crucial for ensuring data quality and making informed decisions about further preprocessing.

```python
plt.figure(figsize=(11, 6))
sns.boxplot(data=df[['University_GPA', 'Starting_Salary', 'Internships_Completed']])
plt.title("Boxplot of Key Numerical Features")
plt.show()
```

![image](https://github.com/user-attachments/assets/b7e31064-21a5-412a-a0a8-90aad315f601)

### 💼 Bar Plot : Average Starting Salary by Field of Study
This bar plot visualizes the average starting salary across different fields of study. By grouping and averaging salary data, it highlights which academic disciplines tend to lead to higher initial earnings. This comparison provides valuable insights for students and educators in understanding how educational choices can impact early career outcomes.

```python
field_salary = df.groupby("Field_of_Study")["Starting_Salary"].mean().sort_values()

# Plot
plt.figure(figsize=(15, 5))
barplot = sns.barplot(
    x=field_salary.values,
    y=field_salary.index,
    hue=field_salary.index,
    palette="viridis",
    legend=False
)

# Add salary values on each bar
for i, value in enumerate(field_salary.values):
    plt.text(value + 100, i, f"${value:,.0f}", va='center')  # Adjust position and format

plt.title("Average Starting Salary by Field of Study")
plt.xlabel("Average Salary")
plt.ylabel("Field of Study")
plt.tight_layout()
plt.show()
```

![image](https://github.com/user-attachments/assets/8cc2a9bd-026e-4621-aa81-bb32b6e27b9f)


## 🚀 Impact on Industry Standards
This project aligns with modern trends in education and workforce analytics by offering actionable insights that support students, educators, and institutions in navigating the path from education to employment.
### 1. Enhancing Career Self-Efficacy
- The analysis empowers students to reflect on **academic performance, internships, and certifications,** helping them better understand their strengths and areas for growth.
- This supports ongoing self-improvement and informed **decision-making moving beyond traditional, one-time career guidance approaches.**
### 2. Enabling Data-Driven Decisions in Education
- The insights generated contribute to institutional strategies by offering **clear, data-backed guidance** on how to improve student outcomes.
- This supports efforts to optimize learning paths, **increase graduation rates, and demonstrate** institutional effectiveness to stakeholders.
### 3. Addressing Real-World Educational Challenges
- In the face of **declining enrollments** and the need for tailored student support, this project provides **scalable, data-driven solutions.**
- These insights help institutions better allocate **resources, enhance retention**, and respond to **changing educational and industry demands**.
### 4. Promoting Lifelong Learning
- By highlighting the impact of **hands-on experiences and skill development**, this project reinforces the importance of continuous learning. 
- It helps students recognize and build on transferable skills, preparing them to **adapt and thrive in dynamic career landscapes.**


## 🛠️ Technologies and Tools
- **Google Colab** – Interactive environment for coding and presenting analysis
- **Python** – Data manipulation, analysis and Visualization
  - Libraries: ```numpy```, ```pandas```, ```matplotlib```, ```seaborn```

## 🏁🔄 Conclusion & Next Steps
This project successfully explored the relationship between students’ educational backgrounds and their early career outcomes. By analyzing factors such as GPA, internships, projects, and learning styles, it uncovered meaningful patterns that influence employability and starting salaries. Through data cleaning, statistical analysis, and powerful visualizations, the project provided actionable insights for students, educators, and institutions. Ultimately, it demonstrates how data-driven strategies can bridge the gap between education and career success, empowering more informed academic and career planning.

### Next Steps:
- **Model Refinement:** Enhance predictive modeling by tuning hyperparameters or testing additional algorithms.
- **Dashboard Integration:** Build an interactive dashboard using tools like Power BI or Streamlit to make insights more accessible.
- **Career Recommendation System:** Develop a system that suggests career paths based on student profiles.

