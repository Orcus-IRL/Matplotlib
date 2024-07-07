 create table of contents copilot

# Matplotlib Learning Journey

Welcome to my Matplotlib learning repository! This project documents my journey as I learn and experiment with Matplotlib, a powerful plotting library for Python.

## Table of Contents
- [Importing necessary modules](#IMPORTING-NECESSARY-MODULES)
- [Loading the Dataset](#LOADING-THE-DATASET)
- [Organizing the Dataset](#ORGANIZING-THE-DATASET-WITH-DATETIME)
- [Line Plot Job_post Vs Months](#LINE-PLOTTING-NUMBER-OF-JOB-POSTS-FOR-EACH-MONTH-JOB_POST-Vs-MONTHS)
- [Bar Plot for Job_title Vs Job_posts](#BAR-PLOT)

## IMPORTING NECESSARY MODULES

```python
import pandas as pd
import matplotlib.pyplot as plt # pyplot is used for GUI plotting inside the IDE
import numpy as np 
from datasets import load_dataset
```

## LOADING THE DATASET

```python
dataset = load_dataset(('lukebarousse/data_jobs'))
df = dataset['train'].to_pandas()
```

## ORGANIZING THE DATASET WITH DATETIME
```python
df.job_posted_date = pd.to_datetime(df['job_posted_date'])
```

## LINE PLOTTING NUMBER OF JOB POSTS FOR EACH MONTH (JOB_POST Vs. MONTHS)

```python
df['job_posted_month'] = df.job_posted_date.dt.month # creating a column where we can have months in one axis and its unique
month_counts = df.job_posted_month.value_counts() # now counting the number of job posting for each months
month_counts = month_counts.sort_index() # sorting that months columns
plt.plot(month_counts.index, month_counts) # line ploting with the index and months column we get a clean plot
```

## BAR PLOT 

```python
job_count = df.job_title_short.value_counts()
job_count = job_count.sort_values(ascending=True)
plt.barh(job_count.index, job_count)
plt.show()
```
