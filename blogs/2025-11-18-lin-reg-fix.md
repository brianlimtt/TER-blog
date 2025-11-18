[← Home](https://brianlimtt.github.io/TER-blog/)<br>

# Fixing a Linear Regression Notebook & Key Lessons Learned

### Quick Access  
- **GitHub Repository:** [Link](https://github.com/brianlimtt/lin-reg-fix/)  
- **Jupyter Notebook (.ipynb):** [Link](https://github.com/brianlimtt/lin-reg-fix/blob/main/assets/lin_reg/linear-regression-tutorial.ipynb)


## Table of Contents
- [1. Common Notebook Issues](#1-common-notebook-issues)
- [2. Managing Dependencies](#2-managing-dependencies)
- [3. Handling Data Structures](#3-handling-data-structures)
- [4. Plotting Best Practices](#4-plotting-best-practices)
- [5. Version Control and GitHub Forks](#5-version-control-and-github-forks)
- [6. Key Takeaways](#6-key-takeaways)
- [7. Predicting House Prices Using a Log-Transformed Linear Model](#7-predicting-house-prices-using-a-log-transformed-linear-model)

---

## 1. Common Notebook Issues

While working through a linear regression tutorial, I encountered several frequent issues:

- Missing packages and modules.
- Errors caused by incompatible data types.
- Outdated or deprecated plotting code that no longer works in modern versions of Python libraries.
- Confusion around using notebook environments and virtual environments.

Understanding these issues upfront can save time and reduce frustration when running Jupyter notebooks from other sources.

---

## 2. Managing Dependencies

Notebooks often rely on multiple Python libraries, and mismatched versions can cause errors. A good practice is to:

- Use a virtual environment to isolate project dependencies.
- Keep a `requirements.txt` file that lists all the packages and versions needed.
- Make sure the notebook uses the correct environment in Jupyter.

This ensures that anyone who opens the notebook can run it without module errors.

---

## 3. Handling Data Structures

Many errors in the notebook came from improper handling of data:

- Pandas Series and DataFrames sometimes need conversion to arrays for certain operations.
- Understanding the structure of your data (shape, dimensions, type) is key for operations like reshaping or regression.

---

## 4. Plotting Best Practices

Plotting in notebooks can be tricky:

- Avoid using outdated libraries or wildcard imports like `from pylab import *`.
- Stick to modern, explicit plotting libraries such as `matplotlib.pyplot` and `seaborn`.
- Label axes clearly, include legends, and separate plots logically for clarity.
- Use residual plots and histograms to analyze regression performance visually.

---

## 5. Version Control and GitHub Forks

When working with notebooks from others:

- Fork the original repository if you don’t have write access.
- Clone your fork locally and make changes in your branch.
- Stage, commit, and push changes to your fork.
- Optionally, create a Pull Request to suggest improvements to the original repository.

This workflow keeps your work organized and allows collaboration without affecting the original project.

---

## 6. Key Takeaways

- Always verify your environment and dependencies before running a notebook.
- Understand your data structures to avoid reshaping and type errors.
- Modern plotting libraries provide clearer and safer visualization tools.
- Using forks and version control ensures safe collaboration.
- Document your workflow so others can replicate your fixes easily.

---

By following these principles, you can confidently work with Jupyter notebooks, fix common issues, and contribute improvements to shared projects.

## 7. Predicting House Prices Using a Log-Transformed Linear Model

After completing the simple linear regression example, we now apply the same workflow to a new dataset: **`log_regression_example.csv`**, which relates house size to price.

### Why We Can’t Use a Simple Linear Model
When plotting **Price vs. Size**, the relationship wasn’t linear — the data curved upward.  
To fix this, we applied a **log transform** to the Size variable, which straightened the pattern and allowed us to fit a proper linear regression.

### Final Model
The best-fitting line after transforming the data is:

$$
\text{Price} = 0.2089 \cdot \log(\text{Size}) - 0.0273
$$

- **Size** is in square meters  
- **Price** is in millions of dollars  

### Example Prediction  
Predict the price of a **1000 m²** property:

$$
\text{Price}(1000) = 0.2089 \cdot \log(1000) - 0.0273 \approx 1.42 \text{ million}
$$

### How to Use the Model Yourself
Replace the Size value with any property area:

$$
\text{Price}(\text{your size}) = 0.2089 \cdot \log(\text{your size}) - 0.0273
$$

## Property Size vs. Price

This plot shows the relationship between property size (m²) and price (million $), with a fitted regression line:

![Log-Transformed Linear Regression](images/log_transformed_linear_regression.png)
