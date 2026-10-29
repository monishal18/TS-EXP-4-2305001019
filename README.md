# EXPERIMENT 4: COMPUTE ACF FOR THE FIRST 35 LAGS
# NAME : MONISHA
# REG NO :2305001019

##  Aim
To compute and plot the Autocorrelation Function (ACF) of a time-series dataset for the first 35 lags and use the ACF pattern to identify a suitable time-series model.

##  Software Required
- Python 3
- Google Colab or Jupyter Notebook
- Pandas
- Matplotlib
- Statsmodels

## Procedure
1. Import the required libraries.
2. Create the time-series data.
3. Plot the original time series.
4. Calculate ACF values for the first 35 lags.
5. Display the ACF values.
6. Plot and interpret the ACF graph.

## Observation
The ACF plot shows the correlation between observations and their previous values at different lags. The pattern helps identify possible time-series models.

- If ACF tails off gradually, an AR model may be appropriate.
- If ACF cuts off after a few significant lags, an MA model may be considered.
- If ACF tails off with oscillation, an ARMA model may be considered.

ACF alone is not sufficient to determine the exact model order. PACF and other diagnostic checks should also be considered.


##  Program
```

import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.stattools import acf
from statsmodels.graphics.tsaplots import plot_acf

# Create time-series data
data = [
    112, 118, 132, 129, 121, 135,
    148, 148, 136, 119, 104, 118,
    115, 126, 141, 135, 125, 149,
    170, 170, 158, 133, 114, 140,
    145, 150, 165, 160, 155, 170,
    190, 188, 175, 160, 145, 165,
    170, 180, 195, 190, 185, 200
]

series = pd.Series(data)

# Plot original time series
plt.figure(figsize=(10, 4))
plt.plot(series, marker="o")
plt.title("Time Series Data")
plt.xlabel("Time")
plt.ylabel("Value")
plt.grid(True)
plt.show()

# Calculate ACF for first 35 lags
acf_values = acf(series, nlags=35)

# Display ACF values
print("ACF Values:")
for lag, value in enumerate(acf_values):
    print("Lag", lag, ":", round(value, 4))

# Plot ACF
plt.figure(figsize=(12, 5))
plot_acf(series, lags=35)
plt.title("ACF for First 35 Lags")
plt.xlabel("Lag")
plt.ylabel("Autocorrelation")
plt.tight_layout()
plt.show()
```
## Expected Output
- Original time-series graph.
<img width="830" height="360" alt="image" src="https://github.com/user-attachments/assets/af2c2595-5eb0-489a-a85f-2707aca3f40c" />

- ACF values from lag 0 to lag 35.
  <img width="607" height="811" alt="image" src="https://github.com/user-attachments/assets/04f74515-a1fe-4256-a349-7d909aa442e5" />

- ACF plot showing autocorrelation bars and confidence limits.
 <img width="832" height="612" alt="image" src="https://github.com/user-attachments/assets/24bb72c1-8504-4e0b-ab19-0d3d37dda912" />



## Result
Thus, the Autocorrelation Function (ACF) was successfully calculated and plotted for the first 35 lags. The ACF pattern can be used to identify a suitable time-series model.
