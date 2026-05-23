# Prediction of Ocean Temperature and Salinity Using Machine Learning

This repository contains a machine learning project focused on the prediction of ocean temperature and salinity using oceanographic data from the CalCOFI dataset.

The goal of the project is to model the relationship between physical and chemical seawater variables and two key target variables: **temperature** and **salinity**. The analysis is performed using **Ridge Regression** combined with **Random Fourier Features**, which approximate an RBF kernel in a computationally efficient way.

## Project Overview

Oceanographic variables often show nonlinear relationships. For this reason, a simple linear regression model may not be flexible enough to accurately predict temperature and salinity.

In this project, the original feature space is transformed using **Random Fourier Features (RFF)**, allowing Ridge Regression to capture nonlinear patterns while avoiding the high computational cost of exact kernel methods.

The project includes:

- Data loading and preprocessing
- Selection of relevant oceanographic variables
- Missing-value analysis and cleaning
- Exploratory data visualization
- Correlation analysis
- Ridge Regression with Random Fourier Features
- Evaluation of prediction performance
- Visualization of actual vs predicted values

## Dataset

The project uses the `bottle.csv` file from the CalCOFI dataset.

The selected variables include:

- Depth
- Temperature
- Salinity
- Dissolved oxygen
- Potential density
- Oxygen saturation
- Oxygen concentration
- Phosphate concentration
- Silicate concentration
- Nitrite concentration
- Nitrate concentration
- Ammonium concentration

The target variables are:

- `T`: temperature in degrees Celsius
- `Salinity`: seawater salinity

## Methodology

The model is based on a pipeline composed of:

1. **Standardization** of the input features
2. **Random Fourier Features** to approximate the RBF kernel
3. **Ridge Regression** for multi-output prediction

Random Fourier Features are used to project the data into a higher-dimensional feature space where nonlinear relationships can be modeled more effectively.

The final model predicts both temperature and salinity at the same time.

## Model Performance

The model achieved strong predictive performance on the test set:

| Metric | Salinity | Temperature |
|---|---:|---:|
| MSE | 0.0028 | 0.0522 |
| R² Score | 0.9828 | 0.9961 |

Overall performance:

| Metric | Value |
|---|---:|
| MSE | 0.0275 |
| R² Score | 0.9894 |

These results show that the model is able to capture the relationship between the selected oceanographic features and the target variables with high accuracy.

## Main Techniques Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Ridge Regression
- RBF Kernel approximation
- Random Fourier Features

## Repository Structure

```text
.
├── notebook.ipynb
├── bottle.csv
└── README.md
