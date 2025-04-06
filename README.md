# Mapping the Student Journey to Career Success | Python
Understanding the transition from education to employment is essential for enhancing career readiness and closing skill gaps. By mapping this journey, we can identify the academic factors, experiences, and skills that most significantly impact outcomes such as job offers, starting salaries, and career satisfaction. This knowledge enables educators, policymakers, and students to make informed decisions that optimize educational strategies and career planning.

## Project Overview
This project dives into the journey from education to employment by analyzing the profiles of 5,000 students. Using Python, it uncovers how academic performance, internships, projects, and learning styles shape career outcomes like job level and salary. The workflow includes data preprocessing, in-depth EDA, and rich visual storytelling through Seaborn and Matplotlib. By mapping out key trends and correlations, the project reveals the most influential factors in achieving career success—offering valuable insights for students, educators, and decision-makers.

## Key Objectives
- **Identify Key Influencers of Career Success**
Analyze how academic performance, internships, projects, and learning styles contribute to better job outcomes and salaries.

- **Bridge the Gap Between Education and Employment**
Uncover insights that can help students, educators, and institutions align learning paths with career opportunities.

- **Support Data-Driven Decision Making**
Provide actionable insights through statistical analysis and visualizations to guide career planning and educational improvements.

- **Highlight the Value of Practical Experience**
Examine the role of internships and hands-on projects in boosting employability and career readiness.

- **Create a Reusable Data Science Workflow**
Build a complete end-to-end data analysis pipeline with data cleaning, EDA, and visualization using Python.

## 📂 Data Details
- Kaggle
<a href="https://github.com/Shakeel-Data/Student-Education-and-Career-Pathways-Python/blob/main/Student%20education%20and%20career%20.csv">csv</a>

## Project Workflow
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
![Column list](https://github.com/user-attachments/assets/1f25f9b7-4f84-4014-8d98-a3dbb29ba343)

```python
df_summary = pd.DataFrame({
    "Column Name": df.columns,
    "Non-Null Count": df.count().values,  # Count of non-null values
    "Data Type": df.dtypes.values
})

df_summary
```
![Column with data](https://github.com/user-attachments/assets/e4df7187-b905-4f35-8de6-c0df57111934)

### 5. Data Cleaning & Preprocessing
Verified and handled missing values, formatted columns, and prepared data for analysis using encoding techniques.

```python
df.isnull().sum()
```
![Data cleaning](https://github.com/user-attachments/assets/94f6998c-8c4f-4ce2-a629-74e750bebfa5)

### 6. Replacing Missing values
Missing value analysis confirms the dataset is clean.


## Exploratory Data Analysis (EDA)
Descriptive statistics and data visualizations offered deeper insights into the dataset. Key summary metrics—such as mean, median, and standard deviation—were used to understand central tendencies and variability. Additionally, visual tools like histograms, countplots, boxplots, and pairplots were employed to explore data distributions, identify outliers, and analyze relationships between variables.

```python
## Data visualization
plt.figure(figsize=(11,6))
sns.histplot(df['Starting_Salary'], bins=30, kde=True)
plt.title("Distribution of Starting Salaries")
plt.show()
```
![Salary distribution](https://github.com/user-attachments/assets/70332c22-3d07-47fb-b2ab-0d2e40a7a235)













































