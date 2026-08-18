# Lab #6 — Keras MLP for Regression

## Overview

This project implements a Multi-Layer Perceptron (MLP) regression model using **Keras/TensorFlow**.

The notebook follows the requirements of Lab #6:

- Dataset loading and exploration
- Missing-value checking
- Feature/target separation
- Feature scaling
- Train/test split
- MLP architecture with multiple hidden layers
- Comparison of ReLU, Sigmoid, and Tanh activation functions
- Comparison of MSE, MAE, and Huber loss functions
- Training and validation loss curves
- Evaluation using MAE, RMSE, and R²
- Activation + loss combination comparison
- Best-model selection
- Actual vs. predicted visualization
- Prediction-error visualization
- Final model saving

## Dataset

The notebook uses the **California Housing dataset** provided through `scikit-learn`.

The target variable is:

`MedHouseVal`

It represents the median house value in units of $100,000.

## Requirements

Install the required Python packages with:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn tensorflow
```

For Google Colab, most packages are already available.

## Files

```text
Lab_6_Keras_MLP_Regression.ipynb
README.md
```

## How to Run

### Option 1 — Google Colab

1. Open Google Colab.
2. Upload `Lab_6_Keras_MLP_Regression.ipynb`.
3. Run the notebook cells from top to bottom.
4. Review the generated tables, graphs, and evaluation metrics.

### Option 2 — Jupyter Notebook

Install Jupyter if necessary:

```bash
pip install notebook
```

Start Jupyter:

```bash
jupyter notebook
```

Open:

```text
Lab_6_Keras_MLP_Regression.ipynb
```

Run all cells sequentially.

## MLP Architecture

The model contains:

```text
Input Layer
     ↓
Dense Layer — 64 neurons
     ↓
Dense Layer — 32 neurons
     ↓
Dense Layer — 16 neurons
     ↓
Output Layer — 1 neuron
```

The output layer contains one neuron because this is a regression problem with one continuous target variable.

## Activation Function Experiments

The notebook compares:

1. ReLU
2. Sigmoid
3. Tanh

The other major training parameters are kept reasonably consistent during the activation-function comparison.

## Loss Function Experiments

The notebook compares:

1. Mean Squared Error (MSE)
2. Mean Absolute Error (MAE)
3. Huber Loss

These are appropriate regression loss functions.

- **MSE** strongly penalizes large errors.
- **MAE** treats errors more uniformly.
- **Huber Loss** combines characteristics of MSE and MAE and can be more robust to large errors/outliers.

## Evaluation Metrics

Each experiment is evaluated using:

### MAE

Mean Absolute Error measures the average absolute difference between actual and predicted values.

Lower MAE is better.

### RMSE

Root Mean Squared Error gives greater importance to larger errors.

Lower RMSE is better.

### R² Score

R² measures how well the model explains the variation in the target variable.

A higher R² is generally better.

## Model Comparison

The notebook creates a comparison table containing:

| Activation | Loss Function | MAE | RMSE | R² |
|---|---|---:|---:|---:|
| ReLU | MSE | Generated after execution | Generated after execution | Generated after execution |
| Sigmoid | MSE | Generated after execution | Generated after execution | Generated after execution |
| Tanh | MSE | Generated after execution | Generated after execution | Generated after execution |
| ReLU | MAE | Generated after execution | Generated after execution | Generated after execution |
| ReLU | Huber | Generated after execution | Generated after execution | Generated after execution |
| Sigmoid | MAE | Generated after execution | Generated after execution | Generated after execution |
| Sigmoid | Huber | Generated after execution | Generated after execution | Generated after execution |
| Tanh | MAE | Generated after execution | Generated after execution | Generated after execution |
| Tanh | Huber | Generated after execution | Generated after execution | Generated after execution |

The actual values are generated when the notebook is executed.

## Best Model Selection

The notebook automatically sorts the experiments by RMSE and displays the best-performing experiment.

The selected model is then retrained and evaluated on the test dataset.

## Visualizations

The notebook generates:

- House-value distribution
- Feature correlation heatmap
- Activation-function validation-loss comparison
- Loss-function validation-loss comparison
- Best-model training vs. validation loss
- Actual vs. predicted values
- Prediction-error distribution

## Overfitting and Underfitting

The learning curves can be used to analyze model behavior.

### Possible Overfitting

If training loss continues decreasing while validation loss starts increasing, the model may be overfitting.

### Possible Underfitting

If both training and validation losses remain high, the model may be underfitting.

## Output Model

At the end of the notebook, the trained final model is saved as:

```text
keras_mlp_regression_model.keras
```

## Important Note

Run the notebook from the first cell to the last cell so that the dataset, preprocessing objects, models, experiment results, and variables are created in the correct order.

The numerical results in the comparison table and final evaluation are generated during notebook execution and may vary slightly depending on the TensorFlow/environment configuration.
