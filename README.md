# 🚗 Car Dataset Analysis using Pandas

This project demonstrates **data cleaning, filtering, and basic analysis** using **Pandas** in Jupyter Notebook.

---

## 🔹 1. Libraries & Functions Used
- `import pandas as pd` → Import Pandas library  
- `pd.read_csv("file.csv")` → Import the CSV file  
- `head()` → Show the first N rows (default N=5)  
- `shape` → Show total number of rows and columns  
- `df.isnull().sum()` → Detect missing values from each column  
- `fillna()` → Fill null values of a column with a particular value  
- `value_counts()` → Show unique values with their count (works on a single column)  
- `isin()` → Filter records including particular elements  
- `apply()` → Apply a function along any axis of the DataFrame  

---

## 🔹 2. Questions Solved

### Q1) **Data Cleaning**  
👉 Find all Null Values in the dataset. If there is any null value in any column, then fill it with the mean of that column.  
```python
df.isnull().sum()
df.fillna(df.mean(numeric_only=True), inplace=True)

Q2) Value Counts

👉 Check what are the different types of Make in the dataset, and what is the count (occurrence) of each.

df["Make"].value_counts()

Q3) Filtering by Origin

👉 Show all the records where Origin is Asia or Europe.

df[df["Origin"].isin(["Asia", "Europe"])]

Q4) Removing Unwanted Records

👉 Remove all the records (rows) where Weight is above 4000.

df = df[df["Weight"] <= 4000]

Q5) Applying Function

👉 Increase all the values of the MPG_City column by 3.

df["MPG_City"] = df["MPG_City"].apply(lambda x: x + 3)
