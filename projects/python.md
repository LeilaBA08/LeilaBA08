# Python Projects

A collection of Python projects completed during my Data Analyst bootcamp, using 
Pandas in Google Colab.

## Contents
- [1. Student Data Analysis with Pandas](#1-student-data-analysis-with-pandas)

---

## 1. Student Data Analysis with Pandas

A group exercise using the `student.csv` dataset, covering the core Pandas workflow 
from loading data through to exporting results, indexing, filtering, aggregation, 
pivot tables, and visualisation.

### Loading and exploring the data

```python
import pandas as pd
df = pd.read_csv('student.csv')
```

I made sure Pandas was imported first, then loaded the student CSV into a DataFrame.

```python
df.head()
```

This shows the first 5 rows of the DataFrame, including the column names.

```python
df.info()
```

This shows information about the DataFrame, including the index, data types, and columns.

```python
df.describe()
```

This shows summary statistics for the numeric columns, in this case, `id` and `mark`.

### Indexing and slicing

```python
df['name']
```

Selects a single column from the DataFrame.

```python
df[['name', 'mark']]
```

To select more than one column, the column names go inside double square brackets.

```python
df.iloc[0:3]
```

Used `iloc` to select rows by their index position, since indexing starts at 0, this 
selects the first 3 rows.

```python
df[df['class'] == 'Four']
```

Filters the DataFrame to only show rows where `class` is equal to "Four".

### Data manipulation

```python
df['passed'] = df['mark'] >= 60
```

Adds a new column, `passed`, which shows `True` or `False` depending on whether each student's mark is 60 or above.

```python
df.rename(columns={'mark': 'score'}, inplace=True)
df.head()
```

Renamed the `mark` column to `score`, then checked `df.head()` to confirm the change 
took effect.

```python
df.drop('passed', axis=1, inplace=True)
```

Dropped the `passed` column. `axis=1` tells Pandas to remove a column rather than a row, and `inplace=True` makes the change to the original DataFrame rather than just 
returning a preview.

### Aggregation and grouping

```python
df.groupby('class')['score'].mean()
```

Groups the DataFrame by `class`, then calculates the mean `score` for each group.

```python
df.groupby('class').size()
```

Groups by `class` again, but this time counts how many students are in each one.

```python
df.groupby('gender')['score'].mean()
```

Groups by `gender` and finds the average score for each group.

### Advanced operations

```python
pd.pivot_table(df, index='class', columns='gender', values='score')
```

Builds a pivot table where each row is a class, each column is a gender, and each cell 
shows the average score for that group.

```python
def get_grade(score):
    if score >= 85:
        return 'A'
    elif score >= 70:
        return 'B'
    elif score >= 60:
        return 'C'
    else:
        return 'D'

df['grade'] = df['score'].apply(get_grade)
```

Created a new `grade` column by applying a function that assigns a letter grade based on the score.

```python
df.sort_values(by='score', ascending=False)
```

Sorts the DataFrame by `score`, with the highest scores at the top.

### Exporting data

```python
df.to_csv('students_with_grades.csv', index=False)
```

Saved the updated DataFrame to a new CSV file, excluding the row index.

### Visualisation

```python
df.groupby('class')['score'].mean().plot(kind='bar')
plt.show()
```

A bar chart showing the average score for each class, making it easy to see at a glance which class scored higher or lower.

---

## Skills Demonstrated

- Loading and exploring data with `read_csv`, `head`, `info`, and `describe`
- Indexing and slicing with column selection, `iloc`, and boolean filtering
- Adding, renaming, and dropping columns
- Grouping and aggregating data with `groupby`
- Building pivot tables
- Writing custom functions and applying them with `apply`
- Sorting data
- Exporting DataFrames to CSV
- Basic data visualisation with Pandas plotting
