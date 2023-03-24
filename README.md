# Custom Missing Data Cleaner

This module provides a Python function, `remove_columns_below_threshold`, that cleans a pandas DataFrame by automatically removing columns containing missing values (such as Null, NaN, or other empty cell symbols) based on a user-defined percentage of compliance.

## Function: remove_columns_below_threshold(df, compliance_threshold)

### Parameters

* `df` (pandas.DataFrame): The input DataFrame to be cleaned.
* `compliance_threshold` (float): The acceptable percentage of missing values in a column. Columns with a higher percentage of missing values will be removed.

### Returns

* `df_clean` (pandas.DataFrame): The cleaned DataFrame with columns removed based on the compliance threshold.
* `columns_to_remove` (list): A list of column names that were removed from the DataFrame.
* `missing_data_stats` (dict): A dictionary containing the missing data statistics for each removed column. The keys are column names, and the values are dictionaries containing 'missing_count', 'missing_percentage', and 'reason' for removal.

### Usage

```python
import pandas as pd

data = {
    'A': [1, 2, None, 4, 5],
    'B': [None, None, None, 4, 5],
    'C': [1, 2, 3, 4, 5],
    'D': ['a', 'b', 'c', 'd', 'e'],
}

df = pd.DataFrame(data)

compliance_threshold = 20  # percentage
df_clean, removed_columns, missing_data = remove_columns_below_threshold(df, compliance_threshold)

print("Clean DataFrame:")
print(df_clean)
print("\nRemoved columns:")
print(removed_columns)
print("\nMissing data statistics:")
print(missing_data)
