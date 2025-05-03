# Fuel-efficiency-prediction
a study of comparing different regressors to predict how a car is fuel efficient


## Overview
This repository contains a Jupyter notebook that explores and models the Auto MPG dataset to predict a car’s fuel efficiency (miles per gallon, MPG) from its technical specifications 

. It compares multiple regression algorithms—from simple linear models to deep neural networks. 

. The analysis includes data cleaning, exploratory analysis model training, and evaluation 


## Dataset

The Auto MPG dataset was donated to the UCI Machine Learning Repository in 1993 and contains 398 instances of cars manufactured between 1970 and 1982, with features such as cylinders, displacement, horsepower, weight, acceleration, model year, origin.

### Features

| Feature        | Type        | Description                                       |
| -------------- | ----------- | ------------------------------------------------- |
| `mpg`          | Continuous  | Fuel efficiency (target variable)                 |
| `cylinders`    | Discrete    | Number of engine cylinders                        |
| `displacement` | Continuous  | Engine size (cubic inches)                        |
| `horsepower`   | Continuous  | Engine power (hp) — some missing values           |
| `weight`       | Continuous  | Vehicle weight (lbs)                              |
| `acceleration` | Continuous  | Time to accelerate from 0–60 mph (sec)            |
| `model_year`   | Discrete    | Year of manufacture (1970–1982)                   |
| `origin`       | Discrete    | Region of origin (1 = USA, 2 = Europe, 3 = Japan) |


## Setup

1. Clone the repository
```
git clone https://github.com/SoheilMehrizi/Fuel-efficiency-prediction.git
cd Fuel-efficiency-prediction
```
2. Install dependencies

```
pip install -r requirements.txt
```

## Usage

1. Launch the notebook

```
jupyter notebook main.ipynb
```

2. Follow the sections:

* Data loading and cleaning

* Exploratory Data Analysis (EDA)

* Feature preprocessing (missing-value handling, encoding)

* Model training

* Evaluation and comparison of algorithms


## Algorithms Compared
* Linear Regression (Single Input): Predicts MPG from Horsepower alone.

* Linear Regression (Multiple Inputs): Full multivariate linear model using all normalized features.

* Deep Neural Network (DNN): Feedforward neural network with two hidden layers (64 units each, ReLU activation) built in TensorFlow/Keras.


Results

The models were evaluated on a held-out test set using Mean Absolute Error (MAE) in MPG:

| Model                                | MAE (MPG) |
| ------------------------------------ | --------: |
| **Linear Regression (Horsepower)**   |   3.64107 |
| **Linear Regression (All Features)** |   2.44260 |
| **Deep Neural Network (DNN)**        |   1.75340 |


The DNN achieved the lowest test MAE, indicating the best predictive accuracy among the compared models.


Saving the Model

The trained DNN model is saved as `dnn_model.keras` and can be loaded via:

```
from tensorflow.keras.models import load_model
model = load_model('dnn_model.keras')
```

## Requirements

* Python 3.8+

* numpy

* pandas

* matplotlib

* seaborn

* tensorflow