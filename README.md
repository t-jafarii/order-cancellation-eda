# Order Cancellation Exploratory Data Analysis

## Overview

This project explores order data to understand order cancellations, rejection patterns, cancellation timing, and estimated arrival time (ETA). The analysis is performed in a Jupyter Notebook using Python, pandas, NumPy, Matplotlib, and SciPy.

The notebook follows the analysis tasks provided for the project and focuses on exploratory data analysis (EDA), descriptive statistics, and visualizations.

## Dataset

The notebook loads the orders dataset from:

```text
input/data_orders.csv
```

Make sure this file is available at that relative path before running the notebook.

The notebook examines the following fields:

| Column | Description |
|---|---|
| `order_datetime` | Time of the order |
| `origin_longitude` | Longitude of the order origin |
| `origin_latitude` | Latitude of the order origin |
| `m_order_eta` | Estimated time before order arrival |
| `order_gk` | Order identifier |
| `order_status_key` | Order status code |
| `is_driver_assigned_key` | Indicates whether a driver was assigned |
| `cancellations_time_in_seconds` | Time elapsed before cancellation, in seconds |
| `order_hour` | Hour extracted from `order_datetime` during the analysis |

### Status codes used in the notebook

- `4`: Cancelled by the customer.
- `9`: Cancelled by the system (rejection).

Other status codes should be interpreted using the dataset's official documentation rather than assumed to represent a particular outcome.

## Analysis

The notebook is organized around four main questions.

### 1. Order failure and cancellation categories

- Examines the distribution of order status codes.
- Compares order counts by status and driver assignment.
- Investigates customer cancellations when a driver has not been assigned and when a driver has been assigned.
- Explores cancellation timing in relation to the available ETA field.
- Examines system cancellations/rejections.

### 2. Failed orders by hour

- Extracts the hour from `order_datetime`.
- Groups orders by hour.
- Visualizes hourly counts for selected cancellation categories, including customer cancellations and system cancellations.
- Looks for hourly patterns in the observed data.

### 3. Cancellation time and outlier exploration

- Compares average cancellation time by hour and driver assignment.
- Uses descriptive statistics and box plots to inspect cancellation-time distributions.
- Explores outliers using both Z-score and interquartile range (IQR) approaches.
- Examines the skewness of the original and filtered cancellation-time data.

Outlier filtering is exploratory: unusual values should not be removed automatically without checking whether they are data errors or valid observations.

### 4. Average ETA by hour

- Calculates average ETA for each order hour.
- Visualizes how the observed mean ETA varies across hours.
- Includes a geographic scatter plot of order origins using longitude and latitude.

## Requirements

Install the Python packages required by the notebook:

```bash
pip install pandas numpy matplotlib scipy jupyter
```

