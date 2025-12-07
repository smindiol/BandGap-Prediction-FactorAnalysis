# Multivariate Analysis and Modeling of Band Gap ($E_g$)

This repository contains the source code and analysis for predicting the Band Gap energy in inorganic non-metal materials, utilizing exclusively descriptors derived from their chemical composition.

## 📋 Project Overview

The primary objective of this project is to explore the statistical structure of atomic properties and evaluate the feasibility of fitting robust regression models on a reduced feature space. The project utilizes the experimental dataset provided by Zhuo et al. (2018).

The workflow includes:
1.  **Feature Engineering:** Generation of 228 statistical descriptors (mean, sum, variance, range) based on 57 atomic properties.
2.  **Dimensionality Reduction:** Implementation of Exploratory Factor Analysis (EFA) to compress the feature space into 20 orthogonal latent factors, eliminating multicollinearity.
3.  **Preprocessing:** Outlier filtering and target variable ($E_g$) transformation using **Box-Cox** to normalize the distribution.
4.  **Modeling:** Training and comparison of regression algorithms (Linear Regression, Ridge, SVR, Random Forest, Gradient Boosting).

## 📊 Key Results

* **Data Structure:** The analysis revealed that the **disparity** (measured by variance and range) among constituent atoms is more determinant for the Band Gap than their average properties.
* **Reduction:** 20 latent factors explain over **83%** of the original variance.
* **Best Model:** **Random Forest** trained on latent factors with Box-Cox transformation.
    * **RMSE:** 0.4627 eV (on transformed scale).
    * **R²:** ~0.78.

## 🛠️ Tech Stack

* **Python 3.x**
* **Pandas & NumPy:** Data manipulation and linear algebra.
* **Factor Analyzer:** For Factor Analysis and adequacy tests (Bartlett, KMO).
* **Scikit-Learn:** Preprocessing, data splitting, and Machine Learning models (SVR, RF, GBM).
* **Matplotlib & Seaborn:** Visualization of factor loadings, decision surfaces, and residuals.

## 📂 Repository Structure

* `/data`: Contains the processed dataset (optional).
* `/notebooks`: Jupyter Notebooks with the step-by-step analysis:
    * `01_Cleaning_and_FeatureEngineering.ipynb`
    * `02_Factor_Analysis.ipynb`
    * `03_Target_Transformation.ipynb`
    * `04_Modeling_and_Evaluation.ipynb`
* `/src`: Helper scripts and functions.

## 📄 Reference

Based on data and initial methodology from:
> Zhuo, Y., Tehrani, A. M., & Brgoch, J. (2018). Predicting the Band Gaps of Inorganic Solids by Machine Learning. *The Journal of Physical Chemistry Letters*, 9(7), 1668-1673.
