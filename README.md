# Stroke Prediction Using Neural Networks

A neural network project for predicting stroke occurrence from patient health and demographic information.

The project explores data preprocessing, exploratory data analysis, neural network design, and the effect of different optimizers and train/test splits on a binary classification problem.

## Overview

The dataset contains patient information such as:

* Gender
* Age
* Hypertension
* Heart disease
* Marriage history
* Work type
* Residence type
* Average glucose level
* BMI
* Smoking status
* Stroke history

The target variable is `stroke`, where:

* `0` represents no stroke
* `1` represents a stroke

## Project Workflow

```text
Patient Dataset
      │
      ▼
Exploratory Data Analysis
      │
      ▼
Categorical Encoding
      │
      ▼
Feature Scaling
      │
      ▼
Train / Test Split
      │
      ├───────────────┐
      ▼               ▼
TensorFlow/Keras    PyTorch
Neural Network      Neural Network
      │               │
      └───────┬───────┘
              ▼
         Evaluation
```

## Data Exploration

The project includes exploratory analysis using:

* Dataset information and statistics
* Missing-value inspection
* Categorical-value analysis
* Correlation analysis
* Interactive visualizations
* 3D visualizations

Sweetviz is also used for automated exploratory data analysis.

## Data Preprocessing

Categorical features are converted into numerical representations using one-hot encoding.

The following categorical features are encoded:

```text
gender
ever_married
work_type
Residence_type
smoking_status
```

The features are then standardized using `StandardScaler`.

The project experiments with both:

* 80/20 train/test split
* 70/30 train/test split

## Neural Network

The project implements a fully connected neural network using TensorFlow/Keras.

The network architecture is:

```text
Input
  │
  ▼
Dense(256, ReLU)
  │
  ▼
Dense(128, ReLU)
  │
  ▼
Dense(64, ReLU)
  │
  ▼
Dense(32, ReLU)
  │
  ▼
Dense(1, Sigmoid)
```

Binary cross-entropy is used as the loss function.

## Optimizers

Different optimization configurations are evaluated.

### SGD

The project tests SGD with learning rates:

```text
0.001
0.01
```

### Adam

Adam is tested with:

```text
0.001
0.01
```

The experiments are performed with different train/test splits to compare their effect on the model.

## PyTorch Implementation

The project also implements the neural network using PyTorch.

The PyTorch model follows the same general architecture:

```text
256 → 128 → 64 → 32 → 1
```

The final layer uses a sigmoid activation for binary classification.

The model is trained using:

* Binary Cross Entropy (`BCELoss`)
* SGD optimizer
* Adam optimizer

The training process runs for 100 epochs and records the training loss for visualization.

## Evaluation

The project evaluates the trained models on the test set and reports classification accuracy.

Training loss curves are also plotted to observe the model's training behavior.

## Technologies

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Seaborn
* Plotly
* Sweetviz
* TensorFlow / Keras
* PyTorch

## Files

```text
Stroke-prediction-using-neural-networks/
│
├── NN_Project.ipynb
├── nn_project.py
└── README.md
```

## The Notebook

The complete notebook version is available in the repository as `NN_Project.ipynb`.

You can also open and run the notebook directly in Google Colab:

[Open NN_Project.ipynb in Google Colab](https://colab.research.google.com/drive/1U-G5rE_nbdzPWsBYlnP3IEhPZ-Mt1W4P?usp=sharing)


## Note

This project is intended for educational and experimental purposes. The model should not be used as a medical diagnostic system.
