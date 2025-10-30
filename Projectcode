# 1.importing libraries
import pandas as pd
df = pd.read_csv("C:/Users/gunam/Downloads/retail_store_sales.csv")
df.head()

# 1.Load the data

import numpy as np
try:
    titanic_df = pd.read_csv("C:/Users/gunam/Downloads/tested.csv")
    print("Titanic Dataset loaded successfully! ✅")
except FileNotFoundError:
    print("Error: 'titanic.csv' not found. Check the file path.")
print("\n--- First 5 Rows ---")
print(titanic_df.head())

print("\n--- Last 5 Rows ---")
print(titanic_df.tail())

print("\n--- DataFrame Shape (Rows, Columns) ---")
print(titanic_df.shape)

# 2.Inspect the data

print("\n--- Column Names ---")
print(titanic_df.columns.tolist()

print("\n--- Data Types (Dtypes) ---")
print(titanic_df.info())

print("\n--- Summary of Numerical Columns ---")
print(titanic_df.describe())

print("\n--- Unique Values in Key Categorical Columns ---")
print(f"Unique values in 'Sex': {titanic_df['Sex'].unique()}")
print(f"Unique values in 'Embarked': {titanic_df['Embarked'].unique()}")
print(f"Value counts in 'Pclass': \n{titanic_df['Pclass'].value_counts()}")
print(f"\nFare counts less than 0: {titanic_df[titanic_df['Fare'] < 0].shape[0]}")

# 3.Check the Missing Values

print("\n--- Missing Value Count (Before Cleaning) ---")
print(titanic_df.isnull().sum())

# 1. 'Age'
titanic_df['Age'].fillna(titanic_df['Age'].median(), inplace=True)

# 2. 'Embarked'
titanic_df['Embarked'].fillna(titanic_df['Embarked'].mode()[0], inplace=True)

# 3. 'Cabin'
titanic_df.drop('Cabin', axis=1, inplace=True)
print("\n--- Missing Value Count (After Cleaning) ---")
print(titanic_df.isnull().sum())

# 4.Handle Duplicates

print(f"\nNumber of duplicate rows found: {titanic_df.duplicated().sum()}")
titanic_df.drop_duplicates(inplace=True)
print(f"Number of duplicate rows after removal: {titanic_df.duplicated().sum()}")

# 5.Data Type Conversion

titanic_df['Survived'] = titanic_df['Survived'].astype('category')
print("\n--- Data Types After Conversion ---")
print(titanic_df.dtypes)

# 6.Rename the Columns

titanic_df.rename(columns={
    'SibSp': 'Siblings_Spouses',
    'Parch': 'Parents_Children'
}, inplace=True)

print("\n--- Column Names After Renaming ---")
print(titanic_df.columns.tolist())

# 7.Save the Cleaned dataset
output_file = 'titanic_cleaned.csv'
titanic_df.to_csv(output_file, index=False)
try:
    reloaded_df = pd.read_csv(output_file)
    print(f"\nCleaned Titanic dataset saved successfully as '{output_file}' and reloaded shape: {reloaded_df.shape} ✅")
except Exception as e:
    print(f"\nVerification failed: {e}")
