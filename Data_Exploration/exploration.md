## [Overview](../index.md)

# 1. Data Exploration

## 2. [Preprocessing](../preprocessing/cleaning.md)

## 3. [Feature Extraction](../feature_extraction/features.md)

## 4. [Model Building](../model_building/model.md)

## 5. [Conclusion](../conclusion/conclusion.md)

### Exploring the Sensor Data

#### 1.1 Data Structure

The challenge data is obtained from prognostic-data-repository of Prognostics Centre of Excellence in NASA. The data is provided as zip compressed text file with 26 column of numbers. Each row is a snapshot of data taken during a single operation cycle; each column is a different variable. 

The columns correspond to :
1)Unit Number
2)Time, in cycles,
3) Operational Setting 1
4) Operational Setting 2
5) Operational Setting 3
6) Sensor Measurement 1
7) Sensor Measurement 2
 ...
26) Sensor Measurement 26

#### 2.2 Data Analysis

As long as the data driven prognostics algorithms (Polynomial fit, ARIMA, MLP) will be used, the underlying physical meaning of each attribute in data set is not important. The main issue here is to uderstand how the data could be modeled with a suitable data driven algorithm. 

The **training set** includes operational data from 100 different engines. In each data set, the engine was run for a variable number of cycles until failure. The lengths of the run varied with a minimum run length of **128** cycles and the maximum length  of **356** cylces.

The **testing set** includes operational data from 100 different engines. The engines in the test dataset and copletely different from engines in the training data set.

##### Importing Libraries
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import matplotlib as mpl
import matplotlib.cm as cm
import seaborn as sns
sns.set(style="ticks")


pd.set_option('display.width', 500)
pd.set_option('display.max_columns', 100)
pd.set_option('display.notebook_repr_html', True)
sns.set(style="ticks")
%matplotlib inline


import seaborn as sns
pd.set_option('display.width', 1500)
pd.set_option('display.max_columns', 100)
pd.set_option('max_rows',100)
sns.set_context('poster') 
```
##### Loading Data
```python
# Input files don't have column names
dependent_var = ['RemainingUsefulLife']
index_columns_names =  ["UnitNumber","Cycle"]
operational_settings_columns_names = ["OpSet"+str(i) for i in range(1,4)]
sensor_measure_columns_names =["SensorMeasure"+str(i) for i in range(1,22)]
input_file_column_names = index_columns_names + operational_settings_columns_names + sensor_measure_columns_names

df_train=pd.read_csv('train_FD001.txt',delim_whitespace=True,names=input_file_column_names)
df_train.shape
```
