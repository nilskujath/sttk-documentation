# yfdownload (Module)

## download_and_resample_yf_data (Function)

```python
download_and_resample_yf_data(
    stock_symbol: str = "AAPL",
    start_date: Optional[str] = None,
    end_date: Optional[str] = None,
    period: str = "1d",
    fallback_to_higher: bool = False,
    include_resample_base_period: bool = False,
    data_dir: Optional[str] = None
) -> None
```

### Summary

Downloads historical market data from Yahoo Finance, resamples it to the desired period, and saves the data to a CSV file. The function automatically handles period fallback if the requested data period is unavailable.


### Parameters

* `stock_symbol (str, optional)`:
The ticker symbol of the stock to download data for. Defaults to "AAPL".
* `start_date (Optional[str], optional)`:
The start date for the data in YYYY-MM-DD format. Defaults to the start of the last full year.
* `end_date (Optional[str], optional)`:
The end date for the data in YYYY-MM-DD format. Defaults to the end of the last full year.
* `period (str, optional)`:
The desired resampling period (e.g., '4m' for 4 minutes, '2h' for 2 hours). Defaults to "1d".
* `fallback_to_higher (bool, optional)`:
Whether to fall back to the next higher period if data for the requested period is unavailable. Defaults to False.
* `include_resample_base_period (bool, optional)`:
Whether to include base period information in the filename if a fallback period is used. Defaults to False.
* `data_dir (str, optional)`:
Directory where the 'sttk-data' folder should be created. If None, the current working directory is used.


### Returns

* `None`:
This function does not return any value. It saves the downloaded and resampled data to a CSV file.


### Exceptions

* `ValueError`:
Raised if data cannot be downloaded for the specified date range or period.
* `ModuleNotFoundError`:
Raised if the sttk module cannot be found when trying to determine the save directory.


## determine_download_period (Function)

```python
determine_download_period(period: str) -> str
```

### Summary

Determines the appropriate download period based on the requested period. Matches the requested period to the closest available download period supported by Yahoo Finance.


### Parameters

* `period (str)`:
The requested period (e.g., '2m', '1h', '1d').

### Returns

* `str`:
The appropriate download period supported by Yahoo Finance.

### Exceptions

* `ValueError`:
Raised if the period format is not supported.


## get_next_lower_period (Function)

```python
get_next_lower_period(current_period: str, fallback_to_higher: bool) -> Optional[str]
```

### Summary

Returns the next lower available period if the current one is deprecated or unavailable. If fallback_to_higher is True, it will return the next higher available period.


### Parameters

* `current_period (str)`:
The current download period that needs to be adjusted.

* `fallback_to_higher (bool)`:
Whether to fall back to a higher period if the current one is unavailable.

### Returns

* `Optional[str]`:
The next available period, or None if no further fallback is possible.


## resample_data (Function)

```python
resample_data(data: pd.DataFrame, period: str) -> pd.DataFrame
```

### Summary

Resamples the data to the desired period using Pandas' resample functionality.


### Parameters

* `data (pd.DataFrame)`:
The data to be resampled.

* `period (str)`:
The desired resampling period (e.g., '2m', '1h', '2d').

### Returns

* `pd.DataFrame`:
The resampled data.


## save_to_csv (Function)

```python
save_to_csv(
    data: pd.DataFrame,
    stock_symbol: str,
    start_date: str,
    end_date: str,
    original_period: str,
    download_period: str,
    include_resample_base_period: bool,
    data_dir: Optional[str]
) -> None
```

### Summary

Saves the resampled data to a CSV file with a descriptive filename in the sttk-data directory. If the sttk-data directory does not exist, it will be created.

### Parameters

* `data (pd.DataFrame)`:
The resampled data to be saved.

* `stock_symbol (str)`:
The stock symbol (e.g., 'AAPL').

* `start_date (str)`:
The start date for the data range.

* `end_date (str)`:
The end date for the data range.

* `original_period (str)`:
The originally requested period (e.g., '2d').

* `download_period (str)`:
The period actually used to download the data (e.g., '1d').

* `include_resample_base_period (bool)`:
Whether to include base period information in the filename if a fallback period is used.

* `data_dir (str, optional)`:
Directory where the 'sttk-data' folder should be created. If None, the current working directory is used.


### Returns

* `None`:
This function does not return any value. It saves the data to a CSV file.

