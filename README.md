# Programming-Assignment-3
A Programming Assignment of Shinade T. Cancino from 2ECEC for her class, Advanced Computer Programming. 

# About the Code

## Problem 1: Loading and Displaying the Dataset
  ####   The task is to load the dataset cars.csv into a pandas DataFrame named ***cars***, then display the first five and last five rows of the dataset.

| Step | Code | Purpose |
|------|------|---------|
|Import Pandas| import pandas as pd | To use pandas functions|
|Load dataset| cars = pd.read_csv("cars.csv")| Reads the CSV file into a DataFrame|
|Display entire dataset| cars | Shows the full dataset|
|Show first 5 rows| cars.head()| Displays the top 5 rows of the DataFrame|
|Show last 5 rows| cars.tail()| Display the bottom 5 rows of the DataFrame|

## Problem 2: Subsetting, Slicing, and Indexing
  ####   Using the DataFrame ***cars***, the program extracts specific information through slicing and indexing.

| Sub-Problem | Code | Purpose/Output |
|------|------|---------|
| a. Display the first five rows with odd-numbered columns | cars.iloc[0:5, ::2] | Selects the first 5 rows and every second column starting from column index 0 |
| b. Display the row that contains the model “Mazda RX4” | cars[cars['Model'] == 'Mazda RX4' | Filters the DataFrame to show only the row for Mazda RX4 |
| C. Find how many cylinders (cyl) the model “Camaro Z28” has | cars.loc[cars['Model'] == 'Camaro Z28', 'cyl'].values[0] | Extracts the cylinder count → Camaro Z28 has 8 cylinders |
| d. Find the cylinders (cyl) and gear type (gear) for “Mazda RX4 Wag”, “Ford Pantera L”, and “Honda Civic” | cars.loc[cars['Model'].isin(['Mazda RX4 Wag', 'Ford Pantera L', 'Honda Civic']), ['Model','cyl','gear']] |Displays: Mazda RX4 Wag → cyl = 6, gear = 4; Honda Civic → cyl = 4, gear = 4; Ford Pantera L → cyl = 8, gear = 5        |
