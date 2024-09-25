# Ex.No: 02 LINEAR AND POLYNOMIAL TREND ESTIMATION
Date:
### AIM:
To Implement Linear and Polynomial Trend Estiamtion Using Python.

### ALGORITHM:
1. Import necessary libraries 
2. Load the dataset
3. Convert dates to a numeric format for analysis.
4. Perform linear regression to find the line of best fit.
5. Fit a polynomial (degree 2) to the data.
6. Create a plot showing the original data and the linear trend line and the ploynomial trend line.
7. Show the plot with labels and a title.

End the program
### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.stats import linregress

# Load the Mulgrave dataset
df = pd.read_csv('/content/mulgrave_data.csv')  # Update with your actual file name

# Convert 'Timestamp' to datetime and set as index
df['Timestamp'] = pd.to_datetime(df['Timestamp'])
df.set_index('Timestamp', inplace=True)

# Prepare the X and Y values
X = np.array(range(len(df)))  # X: index as numeric
Y = df['Level']  # Change 'Level' to the column you want to analyze

# Linear Trend Estimation
slope, intercept, r, p, std_err = linregress(X, Y)
linear_trend = slope * X + intercept

plt.figure(figsize=(10, 6))
plt.plot(df['Level'], label='Original')  # Adjust based on the column name
plt.plot(linear_trend, label='Linear Trend', color='orange')
plt.legend(loc='best')
plt.title('Linear Trend Estimation for Mulgrave Dataset')
plt.xlabel('Date')
plt.ylabel('Level')
plt.show()

# Polynomial Trend Estimation (degree 2)
coeffs = np.polyfit(X, Y, 2)
poly_trend = np.polyval(coeffs, X)

plt.figure(figsize=(10, 6))
plt.plot(df['Level'], label='Original')  # Adjust based on the column name
plt.plot(poly_trend, label='Polynomial Trend (degree 2)', color='green')
plt.legend(loc='best')
plt.title('Polynomial Trend Estimation for Mulgrave Dataset')
plt.xlabel('Date')
plt.ylabel('Level')
plt.show()

```

### OUTPUT
A - LINEAR TREND ESTIMATION

![Screenshot 2024-09-25 094717](https://github.com/user-attachments/assets/bd3d044e-910a-4a4d-b03b-b684d7b9f7ba)


B- POLYNOMIAL TREND ESTIMATION

![Screenshot 2024-09-25 094727](https://github.com/user-attachments/assets/f56d1fbc-6ac8-472b-ab62-26032cce4948)


### RESULT:
Thus the python program for linear and Polynomial Trend Estiamtion has been executed successfully.
