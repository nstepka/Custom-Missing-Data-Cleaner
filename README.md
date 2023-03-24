Custom Missing Data Cleaner
This module provides a Python function that cleans a pandas DataFrame by automatically removing columns containing missing values (such as Null, NaN, or other empty cell symbols) based on a user-defined percentage of compliance.

Function: remove_columns_below_threshold
This function takes a pandas DataFrame and a compliance threshold percentage as input arguments, removes the columns with missing values exceeding the threshold, and returns the cleaned DataFrame along with the details of removed columns.

Parameters
df: pandas DataFrame
The input DataFrame to clean.
compliance_threshold: float
The acceptable compliance percentage for missing values. Columns with missing value percentages exceeding this threshold will be removed.
Returns
df_clean: pandas DataFrame
The cleaned DataFrame with columns containing missing values exceeding the threshold removed.
columns_to_remove: list
The list of column names that were removed from the DataFrame.
missing_data_stats: dict
A dictionary containing the missing data statistics for each removed column, including the count of missing values, the percentage of missing values, and the reason for removal.
