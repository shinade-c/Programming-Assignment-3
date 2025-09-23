# Programming-Assignment-3
A Programming Assignment of **Shinade T. Cancino** from 2ECEC for her class, **Advanced Computer Programming**.

---

### Overview
This repository contains Python programs using **Pandas** to practice loading datasets, displaying data, subsetting, slicing, and indexing. The problems are:

***1. Loading and Displaying the Dataset*** — loads `cars.csv` into a DataFrame and displays the first and last five rows.

***2. Subsetting, Slicing, and Indexing*** — extracts specific information from the DataFrame using Pandas methods.

This README provides **step-by-step explanations for every line of code**, making the logic and flow clear.

---

### How to Run
1. Open Jupyter Notebook.
2. Ensure `cars.csv` is in the same directory as your notebook.
3. Run the cells from top to bottom:
   - Press **Shift + Enter** on each cell, or
   - Click the **play icon**.
> [!TIP]
> Make sure your Python kernel is active. </br>
> Outputs will appear inline after each cell.

---

### Problem 1: Loading and Displaying the Dataset
> Load the dataset `cars.csv` into a Pandas DataFrame named `cars` and display its first and last five rows.

***Full Code:***
```python
import pandas as pd                   #Import the pandas library

cars = pd.read_csv("cars.csv")        #Load the dataset into a DataFrame called cars
cars                                  #Display the entire DataFrame

cars.head()                           #Display the first five rows of the DataFrame

cars.tail()                           #Display the last five rows of the DataFrame
```
***Cell 1: Import Pandas and Load Dataset***
```python
import pandas as pd
cars = pd.read_csv("cars.csv")
cars
```

**Explanation:**
1. `import pandas as pd` → Imports the Pandas library to work with tabular data.
2. `pd.read_csv("cars.csv")` → Reads the CSV file into a Pandas DataFrame.
3. `cars = ...` → Stores the dataset in the variable cars.
4. `cars` → Displays the full DataFrame in the notebook.

***Cell 2: Display First 5 Rows***
```python
cars.head()
```

**Explanation:**
1. `cars.head()` → Shows the first five rows of the DataFrame.
      - Useful to quickly preview the top of the dataset
  
***Cell 3: Display Last 5 Rows***
```python
cars.tail()
```

**Explanation:**
1. `cars.tail()` → Shows the last five rows of the DataFrame.
2. Useful to inspect the bottom of the dataset.
> Flow: Dataset loaded → first 5 rows displayed → last 5 rows displayed.

*Example Outputs:*
- First five rows
<img width="1137" height="406" alt="image" src="https://github.com/user-attachments/assets/545f0250-7e3f-4c2c-8adf-fa22ff2d68f7" />

- Last five rows
<img width="1079" height="360" alt="image" src="https://github.com/user-attachments/assets/5608d3ab-67a2-4c96-839c-e8bce4bc1fdf" />

---
### Problem 2: Subsetting, Slicing, and Indexing
> Extract specific information from the `cars` DataFrame using slicing, indexing, and conditional selection.

***Full Code:***
```python
import pandas as pd

cars = pd.read_csv("cars.csv")                                                                                  #Load the dataset into a DataFrame called cars
cars #Display the entire DataFrame

cars.iloc[0:5, ::2]                                                                                             # a. Display the first five rows with odd-numbered columns 
                                                                                                                # ::2 means select every other column starting from index 0 
    
(cars[cars['Model']=='Mazda RX4'])                                                                              # b. Display the row that contains the 'Model' of 'Mazda RX4'

cylinders = cars.loc[cars['Model'] == 'Camaro Z28', 'cyl'].values[0]                                            # c. Display how many cylinders does Camaro Z28 have
print("Camaro Z28 has", cylinders, "cylinders.")

(cars.loc[cars['Model'].isin(['Mazda RX4 Wag', 'Ford Pantera L', 'Honda Civic']), ['Model', 'cyl', 'gear']])    # d. Display the cylinders and gear type for Mazda RX4 Wag, Ford Pantera L, and Honda Civic
```

***Cell 1: Import pandas***
```python
import pandas as pd
```

**Explanation:**
1. `import pandas as pd` imports the pandas library, a powerful tool for working with tabular data.
      - `pd` is the alias commonly used to call pandas functions.

***Cell 2: Load dataset into a DataFrame***
```python
cars = pd.read_csv("cars.csv")
cars
```

**Explanation:**
1. `pd.read_csv("cars.csv")` reads the CSV file into a DataFrame, which is like a table in Python.
2. `cars = ...` stores the dataset in the variable `cars`.
3. `cars` on the last line of the cell displays the full DataFrame in Jupyter Notebook.

***Cell 3a: Display the first five rows with odd-numbered columns***
```python
cars.iloc[0:5, ::2]
```

**Explanation:**
1. `cars.iloc[...]` allows index-based selection of rows and columns.
2. `0:5` selects the first five rows (row indices 0 to 4).
3. `::2` selects every other column starting from index 0, i.e., odd-numbered columns.
> The result shows a subset of the DataFrame with only the specified rows and columns.

***Cell 3b: Display the row for Mazda RX4***
```python
(cars[cars['Model']=='Mazda RX4'])
```

**Explanation:**
1. `cars['Model']` == 'Mazda RX4' → Creates a boolean mask where the model is "Mazda RX4".
2. `cars[...]` → Filters the DataFrame to only that row.
> The result is a DataFrame containing all columns for the `'Mazda RX4'` model.

***Cell 3c: Find Cylinders for "Camaro Z28"***
```python
cylinders = cars.loc[cars['Model'] == 'Camaro Z28', 'cyl'].values[0]
print("Camaro Z28 has", cylinders, "cylinders.")
```

**Explanation:**
1. `cars.loc[...]` allows label-based selection of rows and columns.
2. `cars['Model'] == 'Camaro Z28'` selects the row where Model is `'Camaro Z28'`.
3. `'cyl'` selects the cylinders column.
2. `.values[0]` → Extracts the integer value of cylinders.
3. `print(...)` → Displays the number of cylinders.

***Cell 3d: Find Cylinders and Gear Type for Selected Models***
```python
(cars.loc[cars['Model'].isin(['Mazda RX4 Wag', 'Ford Pantera L', 'Honda Civic']), ['Model', 'cyl', 'gear']])
```

**Explanation:**
1. `cars['Model'].isin([...])` creates a boolean mask for rows where the Model is one of the specified models.
2. `cars.loc[mask, ['Model', 'cyl', 'gear']]` selects the rows that match the mask and only the specified columns: `'Model'`, `'cyl'`, and `'gear'`.
3. The resulting DataFrame shows the cylinders and gear type for `'Mazda RX4 Wag'`, `'Ford Pantera L'`, and `'Honda Civic'`.

*Example Outputs:*
- First five rows with odd-numbered columns

  <img width="640" height="366" alt="image" src="https://github.com/user-attachments/assets/3d1b2647-bfbc-4fa9-b2e4-8ff7c5552b8b" />
- Row that contains the 'Model' of 'Mazda RX4'
  <img width="1024" height="135" alt="image" src="https://github.com/user-attachments/assets/4811e73d-6810-468d-80d6-1338edd6116f" />
- Cylinders of Camaro Z28

  <img width="403" height="52" alt="image" src="https://github.com/user-attachments/assets/8cbc13bf-a7ac-4605-986a-ed70ce39c7f2" />
- Cylinders and gear type for Mazda RX4 Wag, Ford Pantera L, and Honda Civic
  <img width="442" height="254" alt="image" src="https://github.com/user-attachments/assets/fe93f789-98ca-41e4-8021-35cd1345ada7" />

---
*Version 2: The README has been completely revised to provide a cell-by-cell explanation of each code segment, making it easier for viewers to understand the flow and logic of the notebook.*
