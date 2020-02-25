# Mod 2 Code Challenge: Northwind Database

This assessment is designed to test your understanding of these areas:

1. Data Engineering
    - Interpreting an entity relationship diagram (ERD) of a real-world SQL database
    - Importing data from a real-world SQL database
    - Data manipulation in SQL and/or Pandas
2. Inferential Statistics
    - Set up a hypothesis test
    - Execute a hypothesis test
    - Interpret the results of a hypothesis test in order to answer a business question

Create a new Jupyter notebook to complete the challenge and show your work. Make sure that your code is clean and readable, and that each step of your process is documented. For this challenge each step builds upon the step before it. If you are having issues finishing one of the steps completely, move on to the next step to attempt every section.

### Setting up a Hypothesis Test

The business question you are trying to answer is:

> Is the mean `quantity` of a product ordered *greater* when the product is discounted, compared to when it is not?

In the Jupyter Notebook, document:

 - The null hypothesis H<sub>0</sub> and alternative hypothesis H<sub>A</sub>
 - What does it mean to make `Type I` and `Type II` errors in this context?

### Importing Data

Contained in this repo is a SQLite database named ***northwind_db.sqlite***.  This database represents a subset of of the Northwind database — a free, open-source dataset created by Microsoft.  It contains the sales data for a fictional company called Northwind Traders.  The full ERD is below.

For your main task, you are only required to utilize the **OrderDetail** table.  Note that the notation used in this ERD differs slightly from the actual SQLite table names.  Recall that you can use the following SQLite command to view a list of all tables in a database:

```
SELECT name FROM sqlite_master WHERE type='table';
```

Using SQL and/or Pandas, import the data contained in the OrderDetail table to begin data cleaning and analysis.

![Northwind ERD](northwind_erd.png)

### Preprocessing Data

Before executing a statistical test, some preprocessing is needed to set up the framing of *when the product is discounted*.  Specifically, create two array-like variables `discounted` and `not_discounted`, based on the values in the `discount` column.  The definition of "discounted" is that `discount` is greater than 0.

### Executing a Hypothesis Test

Run a statistical test on the two samples, `discounted` and `not_discounted`.  Use a significance level of &alpha; = 0.05.

You may import the functions stored in the `flatiron_stats.py` file to help perform your hypothesis tests. It contains the stats functions from the Learn.co lessons: `welch_t(a,b)`, `welch_df(a, b)`, and `p_value(a, b, two_sided=False)`.

Note that `scipy.stats.ttest_ind(a, b, equal_var=False)` performs a two-sided Welch's t-test and that p-values derived from two-sided tests are two times the p-values derived from one-sided tests. See the [documentation](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.ttest_ind.html) for more information.

### Interpreting Results

What do the results of your hypothesis test indicate?  Frame this answer for a business audience.  Consider utilizing visualizations to support your recommendation to Northwind Trading.
