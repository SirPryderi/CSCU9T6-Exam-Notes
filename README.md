# TOC
<!-- START TOC -->
* [Data Mining](#data-mining)
  * [Introduction](#introduction)
    * [What is data mining](#what-is-data-mining)
    * [Data mining Process](#data-mining-process)
    * [Origin of data](#origin-of-data)
    * [Problems with data](#problems-with-data)
    * [Data mining techniques](#data-mining-techniques)
    * [Glossary](#glossary)
  * [Data Preparation](#data-preparation)
    * [Distribution](#distribution)
    * [What to look at in a distribution](#what-to-look-at-in-a-distribution)
      * [Outliers](#outliers)
      * [Minority values](#minority-values)
      * [Data Balancing](#data-balancing)
      * [Data Quantity](#data-quantity)
      * [Noise and Variability](#noise-and-variability)
  * [Classification](#classification)
  * [Data Visualisation](#data-visualisation)
  * [Prediction](#prediction)
  * [Data Mining Project](#data-mining-project)
  * [Logistic Regression](#logistic-regression)
* [Reasoning Systems](#reasoning-systems)
  * [Rule-based Systems (RBS)](#rulebased-systems-rbs)
    * [Deductive inference](#deductive-inference)
      * [Forward Chaining](#forward-chaining)
      * [Backward Chaining](#backward-chaining)
  * [Certainty factors in RBS](#certainty-factors-in-rbs)
  * [Fuzzy Logic](#fuzzy-logic)
  * [Case-based Reasoning](#casebased-reasoning)
    * [Procedure](#procedure)
    * [Similarity](#similarity)
    * [Adaptation](#adaptation)
    * [Advantages and Disadvantages](#advantages-and-disadvantages)
* [Bayesian Belief Networks](#bayesian-belief-networks)
<!-- END TOC -->

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
## Rule-based Systems (RBS)
**Expert systems** aim to caputre the **knowledge** of a human expert in a doman and embody it within a **software** system.

Rule-based systems have the following:

- **Knowledge base** ─ Rules embodying expert knowledge about the problem domain.
- **Database** ─ Contains a set of known facts about the problem domain.
- **Inference engine** ─ carries out the reasoning process, using rules and facts.
- **Explaination Facilities** ─ Provides information to users about the reasoning steps that are being followed.
- **User interface** ─ communication between the user and the system.

![expert-system-architecture]

**Expert System Shells** are programs and or/framework that can be customised to create a RBS. They are known as **shells** or **rule engines**.

The shell usually provides the _inference engine_, _explaination facilities_, and _infrastructure_ for populating the knowledge base and the rules. Sometimes, they also provide interfaces for both users and developers.

The **inference process** used in a RBS is **deductive inference**, meaning that rules of logic are used to create new knowledge combining previous knowledge and rules.

### Deductive inference
There are two main approaches to deductive inference:
- **Forward Chaining**
- **Backward Chaining**

#### Forward Chaining
Forward chaining uses rules like:

		If A and B Then C
		
To increase the number of facts in knowledge base.

The problem with this approach is controlling it. Different rules might be valid at different times, so you need to **indentify** (matching) them, and **decide** which one to use (conflict resolution). 
This makes it useful for RBS with **no specific goal**.

#### Backward Chaining
Backward chaining uses rules like:

		C If A and B
		
The system tries to justify all the subrules that satisfies the **goal** until an answer is found. This might lead to many dead-ends before a solution. 

## Certainty factors in RBS
To improve the working of an RBS, a way of representing the degree of uncertainty related to both facts and rules.

There are many reasons why uncertainty is introduced:
- Information is incomplemte
- Information is not reliable
- Language use imprecise
- There is conflicting information
- Information is approximate

**Certainty factors**, also known as _confidence factors_, are a measure which represents a degree of confidence that some condition is _true_.

Certainty factors have to be combined when two rules are combined together.

		CF(A and B) = min(CF(A), CF(B))
		CF(A or  B) = max(CF(A), CF(B))
		
When applying a rule such as:
		
		If P Then Q @ n

The uncertainty factor of Q is obtained by combining the CF of the rule and the CF of the fact

		CF(Q) = CF(P) · n
		
Altought Confidence Factors resembles **probability**, they are not the same. There is no rigorious mathematical foundation for CF. They are often altered with the design, and there is no strict way of evaluating the certainty of a rule and/or fact. More often than not though, they are extremely effective in practical applications.

Older RBS used Bayesian probability to handle uncertainty.

This model assumes that:
- Hypotesis are mutually exclusive and exhaustive
- Piece of evidence are conditially independent

This mode is usually inaccurate, because the assumptions above are mostly never true, but this model has evolved into **belief networks** that are not giving very promising results.

## Fuzzy Logic
**Fuzzy logic** is an alternative method to boolean logic for determining the value of a property. Instead of being either true or false, a percentage of how much the current condition fits a definition is used.

For instance, the temperature could be either be represented by a boolean `cold, not cold` (_boolean_) or a set of values could be defined `20% Cold` (_fuzzy_), specifying a degree of how much the value fits in that category (_fuzzy measure_).

Fuzzy set theory and fuzzy logic provide a precise and mathematical basis for reasoning about uncertainty.

Fuzzy sets can be effectively shown in graphs, allowing to calculate the corresponding degree given the measurement. The actual measurement is definited as opposite of fuzzy _crisp_.

![age-fuzzy-graph]

Fuzzy Sets can be used in RBS to define how much something fits a certain quality, instead of using an arbitrary change point with a specific temperature.

This is extremely successful in automatic control systems, like washing machines, air conditioner, etc.

### Defuzzification
Defuzzification is the process of producing a quantifiable result in Crisp logic, given fuzzy sets and corresponding membership degrees. It is the process that maps a fuzzy set to a crisp set. It is typically needed in fuzzy control systems.

A common and useful defuzzification technique is center of gravity.

### Hedges
Qualifying words could be provided using a mathematical definition.

Given a function `f` taking values `T`, the following could be defined:

		very_f(T) = f(T)²
		not_f(T) = 1 - f(T)
		slightly_f = f(T)¹ᐟ²
		
## Case-based Reasoning
Another important Reasoning System is Case-Based reasoning. Differently from rule-based systems, and fuzzy logic, **does not use inference** (rules or logical deduction). CBR relies on the **analogy** between a problem a previous one, looking for the most similar problem that has been solved in the past, and applying the same solution.

In a CBR knowledge is stored as a **record of cases**. 

### Procedure
The steps towards creating a CBR are:
- Identifying attributes
- Identify cases
- Compare a new case, with the record of cases

![cbr-architecture]

To solve a new problem, the system does the following:
- **Retrieve** the most similar case(s) from the library
- **Reuse** the case(s) atempt to solve the problem
- **Revise** the proposed solution if necessary
- **Retain** the new solution as part of a new case

### Similarity
CBRs often use the **nearest neighbour algorithm** to find the most similar case. This algorithm uses the distance of two points in a n-dimensional space.

The nearest neighbour approach is only effective with **numerical values**, for **nominal values** another way of specifying how much something is similar to something else must be specified. **Tables**, **Taxonomies**, **Ordered Lists**, etc are possible solutions.

**Taxonomy-based comparison** is suitable for comparing nominal values that can be classified into groups.

![food-taxonomy]

### Adaptation
After having found the best match, the solution might need **adaptation**, since the case won't probably be the exact same. The system might either require a human expert to intervene, or use some other tool, like a neural network to adapt the results to the current case.

The newly created case, should not be directly added to the case-base, or it will become progressively **degraded**. They should first be analysed and accepted.

### Advantages and Disadvantages

**Advantages**
- Knowledge based on previous data
- Causal relationships don't need indentification
- Less formal logic required
- Adding new knowledge is simple
- No need for general rules
- Most people reason by analogy

**Disadvantages**
- Indentify the most signifcant attributes
- All the attributes values must be found
- Decide an algorithm to measure similarity
- Make an effective adaptation strategy

**When to use CBR**
- There are records of previously solved cases
- Historical cases are used to solve new cases
- Human experts tend talk about examples, rather than rules
- The problem domain is not well-defined or well-understood
- Experience is as important as theoretical knowledge

---

# Bayesian Belief Networks

## Probability

The probability is calculated as: `positive outcomes ÷ total outcomes`. 

Probabilities can be combined:

		P(a OR b) = P(a) + P(b) // Disjoint and undependent
		
		P(a OR b) = P(a) + P(b) - P(a ∩ b)
		
		P(a AND b) = P(a) · P(b) // Disjoint and undependent
		
		P(a AND b) = P(a | b) · (b)
		
		not P(a) = 1 - P(a)
		
The **conditional probability** is the probability of `a` knowing that `b` has happened, and is written as:
		
		P(a | b)
		
If `P(a | b) = P(a)` then `a` is completely unrelated to `b`.

## Bayes' Theorem

In general `P(a | b) ≠ P(b | a)`, but `P(a | b) * P(b) = P(b | a) * P(a)` (because of the product rule), thus:

		P(a | b) = P(b | a) · P(a) ÷ P(b)

This is known as the **Bayes' Theorem**, and allows to determine the probabiliy of _a_ given _b_, from the probability of _b_ given _a_.

[histogram]: https://media1.shmoop.com/images/algebra/alg_probstat_picsingvar_narr_graphik_14.png
[expert-system-architecture]: http://cinuresearch.tripod.com/ai/www-cee-hw-ac-uk/_alison/ai3notes/esarch.jpg
[age-fuzzy-graph]: https://c.mql5.com/2/20/fuzzy_set_age.png
[cbr-architecture]: https://www.intechopen.com/source/html/19336/media/image6.png
[food-taxonomy]: https://cdn.datafloq.com/cms/2016/06/01/taxonomy-food.jpg
