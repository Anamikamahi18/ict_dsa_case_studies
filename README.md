# Customer Churn Prediction

## Overview
Machine learning project to predict telecom customer churn.

## Objectives
- Perform EDA
- Preprocess data
- Engineer features
- Train multiple ML models
- Tune hyperparameters
- Compare performance

## Models Used
- Logistic Regression
- KNN
- Naive Bayes
- SVM
- Decision Tree

## Best Model
Tuned Logistic Regression

## Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

## Business Recommendations
- Improve retention for monthly-contract customers
- Provide loyalty offers
- Monitor high-charge customers
- Improve customer support

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook



# Socioeconomic Group Discovery Using Census Data

## Problem Statement

A policy think tank wants to identify **hidden socioeconomic segments** in the adult population of the United States using **1994 Census Adult Income data**.

Instead of relying on predefined income labels such as `<=50K` and `>50K`, the objective is to discover **latent population groups** using **unsupervised machine learning techniques** based on demographic, education, occupation, and work-related features.

The identified groups can help policymakers design better welfare schemes, employment programs, financial literacy initiatives, and economic policies.

---

## Objective

The main objective of this project is to:

- Discover hidden socioeconomic groups using **clustering algorithms**
- Perform **data preprocessing and feature engineering**
- Handle **missing values and outliers**
- Scale numerical features for clustering
- Explore feature relationships using **EDA**
- Reduce dimensionality using **PCA**
- Apply **KMeans Clustering**
- Apply **Agglomerative Clustering**
- Interpret and profile discovered clusters
- Compare clusters with actual income labels **without using income during training**
- Suggest possible **policy interventions**

---

## Dataset Overview

The dataset contains demographic and socioeconomic information of U.S. adults.

### Numerical Features
- age
- fnlwgt
- education-num
- capital-gain
- capital-loss
- hours-per-week

### Categorical Features
- workclass
- education
- marital-status
- occupation
- relationship
- race
- sex
- native-country

### Target-like Column (Not Used in Training)
- income

> Note: Since this is an **unsupervised learning problem**, the `income` column was excluded during model training and used only later for interpretation.

---

## Project Workflow

### Step 1: Data Loading & Understanding
- Loaded dataset
- Checked dataset shape
- Inspected column names and datatypes
- Examined missing values

---

### Step 2: Missing Value Handling
Missing values were identified and handled using:

#### Numerical Columns
- Median Imputation

#### Categorical Columns
- Mode Imputation

This ensures no missing values remain before clustering.

---

### Step 3: Outlier Detection & Treatment
Outliers were analyzed using:

- Boxplots
- Histograms

#### Method Used
**IQR (Interquartile Range) Capping**

Outliers in:
- `age`
- `hours-per-week`

were capped to reduce skewness while preserving information.

The `fnlwgt` column was removed due to limited interpretability for clustering.

---

### Step 4: Feature Selection
Redundant columns were removed:

- `education-num`
- `income`

#### Reason
- `education-num` overlaps with `education`
- `income` must not be used in unsupervised clustering

---

### Step 5: Encoding Categorical Variables
Categorical variables were transformed using:

#### One-Hot Encoding

This converts text categories into machine-readable numerical features.

---

### Step 6: Feature Scaling
Feature scaling was applied using:

#### StandardScaler

Scaling ensures all features contribute equally during distance-based clustering.

---

### Step 7: Exploratory Data Analysis (EDA)

### Correlation Analysis
A heatmap was created to analyze correlations among numerical features.

#### PCA (Dimensionality Reduction)
Principal Component Analysis (**PCA**) was used to:

- Reduce high-dimensional feature space
- Visualize clusters in 2D

---

### Step 8: KMeans Clustering

#### Choosing Optimal K

Two methods were used:

##### Elbow Method
To analyze WCSS (Within Cluster Sum of Squares)

##### Silhouette Score
To evaluate cluster separation quality

Based on these methods:

#### Final Choice
**K = 4**

---

### Step 9: Final KMeans Model
KMeans clustering was trained with:

- `n_clusters = 4`
- `random_state = 42`

Cluster labels were added to the dataset.

Clusters were visualized using PCA.

---

### Step 10: Agglomerative Clustering

Agglomerative clustering was also performed for comparison.

#### Important Note
Since hierarchical clustering is computationally expensive on large datasets, a **sampled PCA dataset** was used.

This avoids memory crashes and runtime failures.

Agglomerative clusters were visualized in 2D PCA space.

---

### Step 11: Cluster Profiling & Interpretation

Each cluster was analyzed using:

#### Numerical Features
Average values of:
- age
- capital-gain
- capital-loss
- hours-per-week

#### Categorical Features
Most dominant categories such as:
- education
- occupation
- marital-status
- relationship
- workclass

#### Income Comparison
Actual income labels were added back **only for interpretation**.

This helped compare discovered clusters against real income distributions.

---

## Policy Suggestions & Business Implications

### Cluster Groups with Lower Income Levels
Recommended for:

- Upskilling programs
- Employment assistance
- Financial literacy programs
- Government welfare support

### Middle Income Groups
Recommended for:

- Career advancement initiatives
- Professional development programs
- Workforce reskilling

### Higher Income Groups
Recommended for:

- Tax planning policies
- Investment awareness programs
- Wealth management initiatives

---

## KMeans vs Agglomerative Clustering

| Aspect | KMeans | Agglomerative |
|--------|--------|----------------|
| Speed | Faster | Slower |
| Scalability | Better | Poor for large datasets |
| Computational Cost | Low | High |
| Dataset Suitability | Better for large datasets | Better for hierarchical analysis |

### Final Decision
KMeans was selected as the primary clustering method due to:

- Better scalability
- Faster computation
- Ability to handle the full dataset efficiently
- Meaningful cluster formation

Agglomerative clustering was used mainly for comparison and visualization purposes.

---

## Conclusion

This project successfully identified hidden socioeconomic groups in the U.S. adult population using **unsupervised learning techniques**.

Without using income labels during training, clustering algorithms discovered meaningful demographic and work-related population segments.

The findings demonstrate how machine learning can assist policymakers in designing:

- Better welfare schemes
- Targeted employment initiatives
- Financial inclusion programs
- Tax-related strategies

The project highlights the power of clustering for discovering hidden patterns in real-world socioeconomic data.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn

---

## Machine Learning Techniques Used

- Missing Value Imputation
- Outlier Treatment (IQR)
- One-Hot Encoding
- Feature Scaling
- PCA
- KMeans Clustering
- Agglomerative Clustering
- Cluster Profiling

---

## Author

**Anamika M**  
Aspiring Data Scientist | Machine Learning Engineer
