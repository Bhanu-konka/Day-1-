# Day-1-
 Objective
To clean and preprocess the Netflix Movies and TV Shows dataset by handling missing values, removing duplicates, standardizing text, converting date formats, and ensuring consistent data types — preparing it for further analysis.

Dataset
Name: Netflix Movies and TV Shows

Source: Kaggle

Link to dataset

Technologies Used
Python

Pandas

NumPy

Jupyter Notebook (or any Python environment)

🔧 Steps Performed
✅ 1. Imported Necessary Libraries
python
Copy
Edit
import pandas as pd
import numpy as np
import warnings
warnings.filterwarnings('ignore')
✅ 2. Loaded the Dataset
python
Copy
Edit
df = pd.read_csv('netflix_titles.csv')
✅ 3. Explored the Dataset
python
Copy
Edit
df.head()
df.shape
df.columns
df.info()
df.describe()
df.isnull().sum()
✅ 4. Removed Duplicate Rows
python
Copy
Edit
df = df.drop_duplicates()
✅ 5. Dropped Rows with Null Values
python
Copy
Edit
# Dropped only critical missing rows
df = df.dropna(subset=['title', 'date_added'])
Or if you dropped all rows with any nulls:

python
Copy
Edit
df = df.dropna()
✅ 6. Standardized Text Columns
python
Copy
Edit
df['country'] = df['country'].str.lower().str.strip()
df['type'] = df['type'].str.lower().str.strip()
df['rating'] = df['rating'].str.upper().str.strip()

# Optional replacements for consistency
df['country'] = df['country'].replace({
    'united states': 'usa',
    'united kingdom': 'uk'
})
✅ 7. Converted Date Format
python
Copy
Edit
df['date_added'] = pd.to_datetime(df['date_added'])
✅ Final Outcome
Cleaned and well-structured Netflix dataset.

No duplicate or null rows (in important fields).

Standardized formatting for text and dates.

Dataset ready for exploratory data analysis or modeling.


