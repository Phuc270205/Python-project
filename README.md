# Movie Correlation Analysis in Python

## Overview
This project explores relationships between movie features such as **budget**, **gross revenue**, **votes**, **score**, and other attributes using **Python**.

The main goal of the project is to identify which factors are most strongly correlated with a movie's financial success, especially **gross earnings**.

This project demonstrates a basic data analysis workflow:
- loading and inspecting data
- checking for missing values
- cleaning and transforming columns
- visualizing relationships
- computing correlation matrices
- identifying strongly correlated variables

---

## Project Objectives
The main questions explored in this project were:

- Is there a strong relationship between **budget** and **gross revenue**?
- Which numeric movie features are most correlated with **gross earnings**?
- Do variables such as **votes**, **score**, or **company** show meaningful correlation with revenue?
- Which movie attributes appear most associated with financial performance?

---

## Tools Used
- **Python**
- **Pandas** — data cleaning and manipulation
- **NumPy** — missing value checks and calculations
- **Matplotlib** — plotting
- **Seaborn** — regression plot and heatmap visualization
- **Jupyter Notebook** — analysis workflow and code execution

---

## Dataset
This project uses a movie dataset loaded from:

- `movies.csv`

The dataset includes columns such as:
- `name`
- `rating`
- `genre`
- `year`
- `released`
- `score`
- `votes`
- `director`
- `writer`
- `star`
- `country`
- `budget`
- `gross`
- `company`
- `runtime`

---

## Project Workflow

### 1. Import Libraries
The project begins by importing:
- pandas
- numpy
- seaborn
- matplotlib

These libraries were used for data manipulation and visualization.

---

### 2. Load and Inspect the Data
The dataset was read into a pandas DataFrame using:

- `pd.read_csv()`

Then `df.head()` was used to inspect the first few rows of the dataset.

---

### 3. Check for Missing Values
A loop was used to calculate the percentage of missing values in each column.

This helped identify which columns required cleaning before analysis.

---

### 4. Clean Missing Data
The following cleaning steps were performed:

- rows with missing `gross` values were removed
- rows with missing `budget` values were removed
- missing `rating` values were replaced with `"Unknown"`

This ensured the most important analysis variables were usable.

---

### 5. Fix Data Types
The following columns were converted to integer format:

- `budget`
- `gross`

This was necessary for proper correlation analysis and plotting.

---

### 6. Sort by Gross Revenue
The dataset was sorted in descending order of `gross` to inspect top-earning movies more easily.

---

### 7. Remove Duplicate Records
Duplicate rows were checked using:

- `df.drop_duplicates()`

This step helps reduce repeated records in the dataset.

---

### 8. Visualize Budget vs Gross Revenue
A scatter plot was created to explore the relationship between:

- `budget`
- `gross`

This gave an initial visual sense of whether higher budgets tend to be associated with higher revenue.

---

### 9. Plot Regression Line
A seaborn regression plot was created for:

- `budget` vs `gross`

This helped show the overall trend more clearly.

---

### 10. Correlation Analysis for Numeric Features
A Pearson correlation matrix was computed using numeric columns only.

This was visualized with a heatmap to identify strong numeric relationships.

---

### 11. Convert Categorical Columns to Numeric Codes
To include non-numeric columns in correlation analysis, object-type columns were converted into category codes.

This allowed the project to calculate correlations across a wider set of features.

---

### 12. Full Correlation Matrix
A new correlation matrix was created using the numerized dataset.

This helped compare relationships between both numeric and encoded categorical variables.

---

### 13. Find High Correlation Pairs
The correlation matrix was reshaped using:

- `.unstack()`

Then sorted to identify the strongest correlation pairs.

A filtered list of pairs greater than `0.5` was created to highlight strong positive relationships.

---

## Key Findings
The notebook concludes that:

- **budget** and **votes** have the strongest correlation with **gross revenue**
- movies with higher budgets generally tend to generate higher gross earnings
- movies with more votes also tend to have stronger revenue performance
- correlation analysis helps identify which factors are most associated with box office success

---

## Visualizations Included
This project includes:

- scatter plot of **budget vs gross**
- regression plot of **budget vs gross**
- heatmap of numeric correlations
- heatmap of correlations after converting categorical variables to numeric codes
