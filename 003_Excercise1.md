# Excercise 1

## Plot the median salary for each job title in the dataset.

```python
#  IMPORTING NECESSARY MODULES
import pandas as pd

import matplotlib.pyplot as plt # pyplot is used for GUI plotting inside the IDE

import numpy as np

from datasets import load_dataset

#  LOADING THE DATASET
dataset = load_dataset(('lukebarousse/data_jobs'))

df = dataset['train'].to_pandas()

df.job_posted_date = pd.to_datetime(df['job_posted_date'])

median = df.groupby('job_title_short')['salary_year_avg'].agg('median').sort_values(ascending=True)

plt.barh(median.index, median)

plt.xlabel('Median Salary')

plt.ylabel('Job Title')

plt.title('Median Salary by Job Title')

plt.show()
```
