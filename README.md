# DEVELOPER NAME :Sriram S
# REG NO:212222240105
# DATE:

# Ex.No: 02 LINEAR AND POLYNOMIAL TREND ESTIMATION

### AIM:
To Implement Linear and Polynomial Trend Estiamtion Using Python.

### ALGORITHM:
Import necessary libraries (NumPy, Matplotlib)

Load the dataset

Calculate the linear trend values using least square method

Calculate the polynomial trend values using least square method

End the program
### PROGRAM:
```
import pandas as pd

# Sample data based on the provided image
df = pd.read_csv('student_performance.csv')


df.head()
```

# A - LINEAR TREND ESTIMATION
```
import numpy as np
import matplotlib.pyplot as plt
from scipy import stats

# Linear trend estimation
x = np.arange(len(df))  # Time or sequential variable
y = df['FinalGrade']

# Perform linear regression
slope, intercept, r_value, p_value, std_err = stats.linregress(x, y)

# Calculate the linear trend
linear_trend = intercept + slope * x

# Plot the original data and the linear trend
plt.plot(x, y, label='FinalGrade', marker='o')
plt.plot(x, linear_trend, label='Linear Trend', color='red')
plt.title('Linear Trend Estimation in Final Grade')
plt.xlabel('Time (Index)')
plt.ylabel('Final Grade')
plt.legend()
plt.show()

print(f"Linear Trend Equation: FinalGrade = {intercept:.2f} + {slope:.2f} * Index")
```
B- POLYNOMIAL TREND ESTIMATION
```
# Polynomial trend estimation (degree 2)
coefficients = np.polyfit(x, y, 2)
polynomial_trend = np.polyval(coefficients, x)

# Plot the original data and the polynomial trend
plt.plot(x, y, label='FinalGrade', marker='o')
plt.plot(x, polynomial_trend, label='Polynomial Trend (Degree 2)', color='green')
plt.title('Polynomial Trend Estimation in Final Grade')
plt.xlabel('Time (Index)')
plt.ylabel('Final Grade')
plt.legend()
plt.show()

print(f"Polynomial Trend Equation: FinalGrade = {coefficients[0]:.2f}*Index^2 + {coefficients[1]:.2f}*Index + {coefficients[2]:.2f}")
```

### OUTPUT
# A - LINEAR TREND ESTIMATION
![download](https://github.com/user-attachments/assets/ba7841bb-e761-4e53-ac8a-2989b0ac4769)
# B- POLYNOMIAL TREND ESTIMATION
![download](https://github.com/user-attachments/assets/561e52e2-7b09-48b2-92bf-83d8c8579fb9)


### RESULT:
Thus the python program for linear and Polynomial Trend Estiamtion has been executed successfully.
