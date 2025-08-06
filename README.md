 📊 Task 2 – Data Visualization & Storytelling

This project was part of a data analyst internship task focused on using Tableau to find insights from retail sales data.

The dataset includes sales transactions from 2010. I cleaned the data, calculated total sales, and built visualizations to highlight key business patterns.


# Key Insights

-  *UK* was the highest revenue-generating country
-  *Regency Cake Stand 3 Tier* was the top-selling product
-  Most orders were for *small quantities*(1–5 items)
-  Sales peaked on *Tuesdays and Fridays*


# Tools Used

- Tableau Public  
- Cleaned CSV dataset (cleaned_online_retail.csv)


# Files

- README.md – Project overview  
- cleaned_online_retail.csv – Cleaned dataset  
- screenshots – Images of all charts
  
 # Data Cleaning Steps
  
  import pandas as pd

# Load the Excel file (first 5000 rows for performance)
df = pd.read_excel("Online Retail.xlsx", nrows=5000)

# Step 1: Drop duplicate rows
df = df.drop_duplicates()

# Step 2: Standardize column names
df.columns = df.columns.str.strip().str.lower().str.replace(' ', '_')

# Step 3: Remove negative values in 'quantity' and 'unitprice'
df = df[(df['quantity'] >= 0) & (df['unitprice'] >= 0)]

# Step 4: Fix data types
df['quantity'] = df['quantity'].astype(int)
df['unitprice'] = df['unitprice'].astype(float)

# Step 5: Remove rows where stockcode contains alphabets
df = df[df['stockcode'].astype(str).str.isnumeric()]

# Step 6: Save the cleaned data
df.to_csv("cleaned_online_retail.csv", index=False)

print("Cleaned dataset saved as 'cleaned_online_retail.csv'")


# Data Cleaning Summary

- Removed duplicates
- Renamed columns to lowercase with underscores
- Removed rows with negative quantity or unit price
- Ensured correct data types for key fields
- Filtered out non-numeric stock codes
- Saved the cleaned data as (cleaned_online_retail.csv)


# Outcome

This project helped me practice visual storytelling, business analysis, and dashboard building using Tableau.

