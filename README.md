## Anomaly Detection in Time Series Data

This repository contains code for anomaly detection in time series data. The code utilizes the Vector AutoRegressive (VAR) model and statistical tests to identify anomalies in the data.

### Requirements

To run this code, you need the following dependencies:

- NumPy
- Pandas
- Seaborn
- Matplotlib
- Scikit-learn
- Statsmodels

### Data

The code reads the time series data from the `./data/data.csv` file. The dataset contains the following columns:

- `time_id`: The timestamp of the data
- `ping_ms`: The ping time in milliseconds
- `temperature_c`: The temperature in degrees Celsius
- `humidity_p`: The humidity percentage

### Data Cleaning

The code performs the following data cleaning steps:

- Converts the `time_id` column to datetime format
- Sets the `time_id` column as the index of the dataframe
- Scales the numerical features using the `StandardScaler`

### Stationarity Testing

The code tests the stationarity of each feature using the Augmented Dickey-Fuller (ADF) test. If a feature is found to be non-stationary, it applies differencing to make it stationary.

### Vector AutoRegressive (VAR) Model

The code fits a VAR model to the data and selects the optimal lag order using the Akaike Information Criterion (AIC). The selected lag order is used for anomaly detection.

### Anomaly Detection

The code calculates the squared errors of the VAR model's residuals and identifies anomalies based on a threshold. Anomalies are defined as observations with squared errors above the threshold.

### Visualization

The code visualizes the correlation between the features using a heatmap. It also plots the original data and the data after removing anomalies for comparison.

### Usage

To use this code, ensure that you have the required dependencies installed. Then, run the script. It will perform anomaly detection on the time series data and display the visualizations.

Feel free to modify the code and experiment with different parameters and techniques for anomaly detection.

### Acknowledgments

The VAR model and anomaly detection techniques used in this code are based on established time series analysis methodologies.

### References

- Pandas: https://pandas.pydata.org/
- Seaborn: https://seaborn.pydata.org/
- Matplotlib: https://matplotlib.org/
- Scikit-learn: https://scikit-learn.org/
- Statsmodels: https://www.statsmodels.org/
