# Cars

## Overview

This repository contains a comprehensive data analysis project focusing on a dataset comprising specifications of various cars. The project is implemented in Python, utilizing the Pandas library for efficient data manipulation and analysis.

## Dataset

The dataset is available as a CSV file and is loaded into a Pandas DataFrame using the following code:

```python
import pandas as pd
Cars = pd.read_csv(r'C:\Users\acer\Downloads\Cars.csv')
```

An initial preview of the dataset can be seen with `Cars.head()`.

## Data Cleaning

The project starts with data cleaning, addressing null values in numeric columns (`Cylinders`, `Length`, `Horsepower`, `Weight`, `Wheelbase`, and `EngineSize`). Null values are filled with the mean of their respective columns to ensure data quality.

```python
# Data Cleaning
Cars['Cylinders'].fillna(Cars['Cylinders'].mean(), inplace=True)
Cars['Length'].fillna(Cars['Length'].mean(), inplace=True)
Cars['Horsepower'].fillna(Cars['Horsepower'].mean(), inplace=True)
Cars['Weight'].fillna(Cars['Weight'].mean(), inplace=True)
Cars['Wheelbase'].fillna(Cars['Wheelbase'].mean(), inplace=True)
Cars['EngineSize'].fillna(Cars['EngineSize'].mean(), inplace=True)
```

## Exploratory Data Analysis

### Make Distribution

The distribution of car makes is explored to understand the diversity of brands in the dataset. The count of each make is obtained, providing insights into the representation of each car make.

```python
# Make Distribution
Cars['Make'].value_counts()
```

## Data Filtering

### Origin Filtering

A subset of the dataset is created by filtering records where the origin is either Asia or Europe.

```python
# Origin Filtering
Cars[Cars['Origin'].isin(['Asia', 'Europe'])]
```

## Data Removal

### Weight-based Removal

Records with a weight above 4000 are removed from the dataset.

```python
# Weight-based Removal
Cars[~(Cars['Weight'] > 4000)]
```

## Column Transformation

### MPG_City Column

The values in the 'MPG_City' column are increased by 3 using the `apply` method and a lambda function.

```python
# Column Transformation
Cars['MPG_City'] = Cars['MPG_City'].apply(lambda x: x + 3)
```

## Conclusion

This repository serves as a comprehensive guide to the Cars Data Analysis project, providing step-by-step insights into data loading, cleaning, exploratory analysis, filtering, removal of unwanted records, and column transformation. The documented steps ensure a clear understanding of the dataset and its preparation for further analysis or machine learning tasks.
