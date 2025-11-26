[← Home](https://brianlimtt.github.io/TER-blog/)

# Predicting High vs. Low Gas Mileage Using the Auto Dataset (ISLR Chapter 4, Question 14)

## Table of Contents
- [Introduction](#introduction)
- [(a) Creating the Binary mpg01 Variable](#a-creating-the-binary-mpg01-variable)
- [(b) Graphical Exploration of Features](#b-graphical-exploration-of-features)
- [(c) Splitting the Dataset](#c-splitting-the-dataset)
- [(d) Linear Discriminant Analysis LDA](#d-linear-discriminant-analysis-lda)
- [(e) Quadratic Discriminant Analysis QDA](#e-quadratic-discriminant-analysis-qda)
- [(f) Logistic Regression](#f-logistic-regression)
- [(g) Naive-Bayes Classification](#g-naive-bayes-classification)
- [(h) K-Nearest Neighbors KNN](#h-k-nearest-neighbors-knn)
- [Model Comparison & Final Conclusion](#model-comparison--final-conclusion)

---

## Introduction

In this project, we analyze the **Auto dataset** from the *ISLR* textbook to build a classification model that predicts whether a car has **high or low gas mileage**. 

We transform the continuous MPG variable into a binary classification label, explore relationships between MPG and other variables, and then apply several classification methods:

- LDA  
- QDA  
- Logistic Regression  
- Naive Bayes  
- KNN  

The goal is to identify which methods perform best and to understand which car features are most predictive of high fuel efficiency.

---

## (a) Creating the Binary mpg01 Variable

We first compute the **median MPG** of all cars in the dataset.  
We then define:

- `mpg01 = 1` if a car's MPG is **above** the median  
- `mpg01 = 0` otherwise  

This new feature converts our regression-style MPG data into a **classification problem**.

---

## (b) Graphical Exploration of Features

We used boxplots, scatterplots, and sigmoid curves to visually analyze how each feature relates to `mpg01`.

The strongest predictors of high vs. low MPG were:

- **weight** – lighter cars strongly correspond to higher MPG  
- **horsepower** – lower horsepower → higher MPG  
- **displacement** – smaller engines = more efficient  
- **cylinders** – 4-cylinder cars tend to be high MPG  
- **acceleration** – moderate relationship, but still useful  

All five features were included in later modeling.

---

## (c) Splitting the Dataset

We split the dataset into:

- **70% training data**
- **30% testing data**

Predictors used:

- weight  
- horsepower  
- displacement  
- cylinders  
- acceleration  

Target:

- mpg01

---

## (d) Linear Discriminant Analysis (LDA)

LDA models the boundary between high- and low-MPG cars assuming equal covariance matrices for both classes.

### **Test Error (LDA): 0.1356**

LDA performed very well, misclassifying only about **13.5%** of cars.

---

## (e) Quadratic Discriminant Analysis (QDA)

QDA relaxes the covariance assumption and allows separate covariance matrices for each class.

### **Test Error (QDA): 0.1356**

QDA produced identical performance to LDA, suggesting that a **linear boundary is sufficient** for this dataset.

---

## (f) Logistic Regression

Logistic regression uses the **sigmoid function** to estimate the probability that a car has high MPG.

### **Test Error (Logistic Regression): 0.1441**

Its performance was slightly worse than LDA/QDA, but still strong.  
This confirms that the relationship between predictors and MPG is mostly linear, but with small non-linearities.

---

## (g) Naive-Bayes Classification

Naive Bayes assumes predictor independence and models each feature distribution separately.

### **Test Error (Naive Bayes): 0.1356**

It matched the performance of LDA and QDA, showing that even with independence assumptions, the features still carry strong signal.

---

## (h) K-Nearest Neighbors (KNN)

We tested values of K from **1 to 20** and evaluated test error.

### **Best K:** The lowest error occurred around moderate values of K  
### **Test Error (Best KNN): 0.1356**

This matches the performance of LDA, QDA, and Naive Bayes.

---

## Model Comparison & Final Conclusion

| Model                 | Test Error |
|-----------------------|-----------|
| LDA                   | 0.1356    |
| QDA                   | 0.1356    |
| Logistic Regression   | 0.1441    |
| Naive Bayes           | 0.1356    |
| Best KNN              | 0.1356    |

### ✔ Key Insights

- **Four models (LDA, QDA, Naive Bayes, KNN)** all achieved the same lowest error (13.56%).  
- **Logistic Regression** performed slightly worse but still competitively.
- The success of linear models suggests that **high- vs. low-MPG cars are linearly separable**.
- The strong predictors — weight, horsepower, displacement, cylinders, acceleration — collectively provide powerful discrimination between classes.

### ✔ Final Takeaway

Cars that are:

- **lighter**,  
- **lower horsepower**,  
- **smaller displacement**,  
- **fewer cylinders**, and  
- **have faster acceleration**

are **far more likely** to have **high MPG**.

This project demonstrates how different classification methods compare and highlights the effectiveness of simple models in well-structured datasets like Auto.

---
