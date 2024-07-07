
# Introduction

This notebook demonstrates a simple example of plotting a sine wave using Python. The following libraries are utilized in this example:

- `pandas`: A powerful data manipulation and analysis library.
- `matplotlib`: A plotting library for creating static, animated, and interactive visualizations in Python.
- `numpy`: A library for the Python programming language, adding support for large, multi-dimensional arrays and matrices, along with a large collection of high-level mathematical functions to operate on these arrays.

## Code Explanation

1. **Import Libraries**:
    ```python
    import pandas as pd
    import matplotlib.pyplot as plt
    import numpy as np
    ```

2. **Generate Data**:
    - `x = np.arange(0, 5, 0.1)`: Generates an array of values starting from 0 to 5 with a step of 0.1.
    - `y = np.sin(x)`: Applies the sine function to each element in the array `x`.

3. **Plot Data**:
    ```python
    plt.plot(x, y)
    plt.show()
    ```

    - `plt.plot(x, y)`: Plots `y` versus `x` as lines and/or markers.
    - `plt.show()`: Displays the plot.

## Visual Output

Executing the above code will produce a plot of a sine wave as shown below:

![Sine Wave Plot](sine_wave_plot.png)

This is a simple yet powerful example of how Python can be used to generate and visualize data.

