# csvinspector (Module)

## csvinspector (Function)

```python
csvinspector(
    csv_file_path: str, 
    rows_to_display: Optional[int] = 5, 
    show_info: bool = True
) -> None
```

### Summary

The `csvinspector` function loads a CSV file into a Pandas DataFrame, optionally displays basic DataFrame information, and displays a specified number of rows. It is compatible with both Jupyter notebooks and standard Python environments.


### Parameters

* `csv_file_path (str)`:
The path to the CSV file that you want to inspect.
* `rows_to_display (Optional[int], default=5)`:
The number of rows to display from the top of the DataFrame. If None, the function displays all rows. Defaults to 5.
* `show_info (bool, default=True)`:
A flag to determine whether to display basic DataFrame information, such as the number of rows, columns, and data types of each column. Defaults to True.

### Returns

* `None`:
This function does not return any value. It displays or prints the contents of the DataFrame and optionally its information.

  
### Exceptions

* `ValueError`:
Raised if the CSV file does not exist, is empty, or cannot be read as a valid CSV.