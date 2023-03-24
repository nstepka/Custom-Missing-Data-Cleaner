**Custom Missing Data Cleaner**
This module provides a Python function that cleans a pandas DataFrame by automatically removing columns containing missing values (such as Null, NaN, or other empty cell symbols) based on a user-defined percentage of compliance.

The user can specify the acceptable compliance percentage when calling the function. If a column has missing values exceeding the compliance threshold, it will be removed from the DataFrame. Additionally, the function stores and returns the details of removed columns, such as the count of missing values and the percentage of missing values, allowing the user to further explore and analyze the removed data if desired.


This example demonstrates how to use the remove_columns_below_threshold function with a pandas DataFrame and a compliance threshold percentage. The function returns the cleaned DataFrame, a list of removed columns, and a dictionary containing the missing data statistics for each removed column.
``from missing_data_cleaner import remove_columns_below_threshold

# Create a pandas DataFrame
data = {
    'A': [1, 2, None, 4, 5],
    'B': [None, None, None, 4, 5],
    'C': [1, 2, 3, 4, 5],
}
df = pd.DataFrame(data)

# Set a compliance threshold (percentage)
compliance_threshold = 20

# Call the function
df_clean, removed_columns, missing_data = remove_columns_below_threshold(df, compliance_threshold)

# The cleaned DataFrame, removed columns, and missing data statistics are returned
print(df_clean)
print(removed_columns)
print(missing_data)``
