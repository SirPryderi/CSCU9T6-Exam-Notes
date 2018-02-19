# Data Mining
## Introduction
### What is data mining
- Data mining aims to discover **patterns** and **rules** from large amount of data.
- Helps with the **prediction** of future _events_ and **classification** of past ones.
- Also known as **KDD**: _Knowledge Discovery in Database_.


### Data mining Process
       Raw Data ← ──────────────────────────────────────── Knowledge
          |                                                    ↑
          ↓                                                    |
    Data Warehouse → Target Data → Transformed Data → Patterns and Rules

### Origin of data
- The data usually comes from measurements of the real world
- Using data from the past, you can predict the future

### Problems with data
- **Errors** ─ data might not be not accurate, or missing/
- **Quantity** ─ data might no be enough to find accurate patterns.
- **Quality** ─ data might not contain the information you need.
- **Cost** ─ data might be too expensive to obtain.

### Data mining techniques
- K-nearest neighbour
- K-means clustering
- Decision trees
- Neural networks
- Market basket analysis
- Logistic regression
- ARIMA ─ _Autoregressive Integrated Moving Average_

### Glossary
- **Data** ─ _Data_ are measurements of _values_ associated with _variables_.
- **Data Model** ─ A representation of some aspects of the _data_, usually performing a _task_.
- **Inference** ─ Querying a _model_ to obtain a prediction from some input _data_.
- **Learning** ─ _Learning_ is the process of using _data_ to build a _model_ capable of performing a _task_.
- **Nominal** ─ Nominal _Variables_ describe a quality, such as gender or colour. They are also known as _categorical labels_.
- **Numeric** ─ _Variables_ can be numeric, accepting numbers as _values_.
- **Task** ─ What the end system is supposed to do.
- **Variable** ─ A property that can be measured and varies.
- **Value** ─ A _variable_ can be assigned to a certain set of _values_.

## Data Preparation
To mine specific knowledge out of some raw data, you need appropriate data.

### Distribution
A **frequency distribution** is a count of how often each variables contains each value in a data set.
For discrete values, like nominal ones, it is simply a count of each category.
For continuous numbers, you need to split in range, and see how often values in those range appears.

The easiest way to **plot** distribution is using an histogram.

![histogram]

### What to look at in a distribution
#### Outliers
Outliers are a small number of values that are much bigger or much smaller than the average.
They are usually errors, or a sign that the recorded data is not complete.

#### Minority values
Values that appear very rarely in the distribution.

#### Data Balancing
Data balance is altering the underlying dataset, like removing or duplicating data,
with the intent of helping training process to produce more accurate results.

#### Data Quantity
How much data do you need to represent the dynamics of the system modelled?

#### Noise and Variability
When plotting two variables into a scatter diagram, they might produce a straight line.
In that case there is a **linear correlation** between the two variables.

They could also lie in a cloud along a straight line. In this case, the spread
around the line is called the **correlation**, and this could be caused by:

- Imperfections in measurements
- Variability caused by other variables
- Randomness

Creating a line that minimise the errors between all the samples, is basically
creating a model for the dataset. The mean distance of the model from each sample
is the **error** of the model, usually referred as _mean square error_ or **MSE**.

Creating model for a relationship that is not linear is much more difficult, and
requires more data.

**Learning** is the process or minimising the MSE, either using linear regression,
or iterative search.

## Classification
## Data Visualisation
## Prediction
## Data Mining Project
## Logistic Regression

---

# Reasoning Systems
## Decision Support 1
## Decision Support 2
## Decision Support 3
## Decision Support 4

---

# Bayesian Belief Networks

[histogram]: https://media1.shmoop.com/images/algebra/alg_probstat_picsingvar_narr_graphik_14.png
