# Prognosis

# Overview

## [Data Exploration]()

## [Preprocessing]()

## [Feature Extraction]()

## [Model Building]()

## [Conclusion]()

### Introduction

Recent developments of complex systems, such as aircraft engines, engineering machines, high-speed vehicles and computer numerical control (CNC) systems have been emphasized by the increasing requirements of on-line health monitoring for the purpose of maximizing its operational reliability and safety. As the core part and power source of aircrafts, the reliable operation of an aero engine is critical for ensuring the reliability and safety of the aircraft, and to maintain its availability, and reduce its maintenance costs. Among them, prognostics and health management (PHM) is an effective approach and one of the most commonly-used. In particular, residual useful life (RUL) estimation is a key technology for PHM. 

In general, RUL estimation is to indicate the system/component lifetime before it can no longer perform its function, which is also an important way to reduce production loss, save maintenance costs and avoid fatal machine breakdowns of the equipment before its failure.


### Objective

The objective of this project is to develop an **intelligent information system to forecast the remaining useful life of aircraft turbofan engines**. The system will take historical data about different turbofan engines then apply suitable data preprocessing.
After data preprocessing three types of algorithms (polynomial curve fitting, ARIMA models and single layer perceptron network) is used to discover different patterns in data and output engines remaining useful life.

The system is trained by the engines historical data to be able to forecast the remaining useful life of other turbofan engines.

During the testing phase, a different dataset is used to confirm the ability of the system to perform well in the remaining life forecast task.

Therefore, the objective is to forecast the number of remaining operational cycles before the failure in the test set, that is, the number of operational cycles after the last cycle that the unit will continue to operate. 

### Data Description

The problem solved in this project is the data challenge problem defined by the [2008 PHM conference data challeneg competition](https://c3.nasa.gov/dashlink/projects/15/). A dataset consisting of multiple multivariate time series is provided. This dataset is further divided into training and testing subset. Each timeseries is from a different instance of the same complex engineered system (referred to as "unit") and the data are from several aircraft engines of the same type. Each unit(engine) starts from a different degrees of initial wear and manufacturing variation which is unknown to the user. The data are contaminated with sensor noise.

The unit is operating normally at the start of each time series, and develops fault at some point during the series. In the training set, the fault grows in magnitude until the system failure. In the test set, the time series ends sometime prior to system failure. 

### Scope of Present Work

The aim of this work is to develop an information system based on data driven prognostics. The present work focuses on the following points:
      1. Developing information system that utilizes more than one algorithm in RUL estimation to achieve the best performance.
      2. RUL estimation is performed indirectly by calculating engine health first then applying smoothing and extrapolating processes.
      3. The features utilized for RUL estimation are greatly optimized to exclude irrelevant features that affect negatively in system
         performance.
      4. Model the health index using polynomial curve fitting, ARIMA models and single layer perceptron.

#### Libraries Used

`Python`
* [Python Standard Library](https://docs.python.org/2/library/): Built in python modules.
* [Numpy](http://www.numpy.org/): Scientific computing with python.
* [Matplotlib](http://matplotlib.org/): Python plotting.
* [Pandas](http://pandas.pydata.org/): Data analysis tools.
* [Scikit-learn](http://scikit-learn.org/stable/): Machine learning toolkit.

`R`
* [dplyr](https://cran.r-project.org/web/packages/dplyr/dplyr.pdf): A Grammar of Data Manipulation
* [data.table](https://cran.r-project.org/web/packages/data.table/data.table.pdf): Fast aggregation of large data
* [anytime](https://cran.r-project.org/web/packages/anytime/anytime.pdf): Anything to 'POSIXct' or 'Date' Converter
* [lubridate](https://cran.r-project.org/web/packages/lubridate/lubridate.pdf): Functions to work with date-times and time-spans
