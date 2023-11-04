# Deep-Learning-Model-Training-and-Analysis-for-Classification

## Overview
This Jupyter Notebook project involves the training and analysis of multiple deep learning models on a given dataset. The main tasks completed in this project are:

1. Data Collection: Download the dataset for training and evaluation.
2. Model Training: Implement and train various models with different configurations.
3. Callback Function: Develop a custom callback function to print micro F1 score and AUC score after each epoch.
4. Model Saving: Save the model at each epoch if the validation accuracy improves.
5. Learning Rate Decay: Implement learning rate decay based on specific conditions.
6. Training Termination: Stop training if NaN values occur in weights or loss, or if validation accuracy doesn't improve in the last two epochs.
7. TensorBoard Integration: Use TensorBoard for model analysis and visualize gradients.
8. Loss Function: Use cross-entropy as the loss function.

## Models Evaluated
The project evaluates four different models with varying configurations:

1. Model 1: Tanh activation, SGD with momentum, RandomUniform initializer.
2. Model 2: ReLU activation, SGD with momentum, RandomUniform initializer.
3. Model 3: ReLU activation, SGD with momentum, HeUniform initializer.
4. Model 4: Experiment with custom configurations to optimize accuracy and F1 score.

## Model 1
```
1. Use tanh as an activation for every layer except the output layer.
2. Use SGD with momentum as an optimizer.
3. Use RandomUniform(0,1) as an initializer.

TensorBoard observations:
- Epoch accuracy:
  - Validation accuracy remained constant at about 0.50858.
  - Training accuracy decreased gradually to a low of 0.4989 and stopped in the third epoch due to the EarlyStop callback.
- Epoch loss:
  - Overall loss: 0.6948 on the validation data and 0.7215 on the training data.
- Epoch learning rate:
  - Learning rate decreased from 0.1 to 0.08518 with an average decay of 10% per epoch and an additional 5% deduction every third epoch.
- Micro F1: 0.491618
- AUC: 0.494529
```

## Model 2
```
1. Use ReLU as an activation for every layer except the output layer.
2. Use SGD with momentum as an optimizer.
3. Use RandomUniform(0,1) as an initializer.

TensorBoard observations:
- Epoch accuracy:
  - Validation accuracy reached 0.50336 at the end of the fifth epoch.
  - Training accuracy decreased gradually to a low of 0.4987 and stopped in the fifth epoch due to the EarlyStop callback.
- Epoch loss:
  - Overall loss: 0.6948 on the validation data and 0.1.3668e+5 on the training data.
- Epoch learning rate:
  - Learning rate decreased from 0.1 to 0.0769499 with an average decay of 10% per epoch and an additional 5% deduction every third epoch.
- Micro F1: 0.664238
- AUC: 0.5
```

## Model 3
```
1. Use ReLU as an activation for every layer except the output layer.
2. Use SGD with momentum as an optimizer.
3. Use he_uniform() as an initializer.

TensorBoard observations:
- Epoch accuracy:
  - Validation accuracy reached 0.6322 at the end of the ninth epoch.
  - Training accuracy reached 0.6528.
  - Training stopped in the ninth epoch due to the EarlyStop callback.
- Epoch loss:
  - Overall loss: 0.6372 on the validation data and 0.624 on the training data.
- Epoch learning rate:
  - Learning rate decreased from 0.1 to 0.06250264 with an average decay of 10% per epoch and an additional 5% deduction every third epoch. This is the lowest learning rate achieved in our previous models.
- Micro F1: 0.430323
- AUC: 0.611149
```

## Model 4
```
TensorBoard observations:
- Epoch accuracy:
  - Validation accuracy reached 0.6724 at the end of the seventh epoch.
  - Training accuracy reached 0.6582.
  - Training stopped in the seventh epoch due to the EarlyStop callback.
- Epoch loss:
  - Overall loss: 0.6056 on the validation data and 0.6084 on the training data.
- Epoch learning rate:
  - Learning rate decreased from 0.1 to 8.1225e-3 with an average decay of 10% per epoch and an additional 5% deduction every third epoch. The low learning rate is due to using the Adam optimizer.
- Micro F1: 0.675547
- AUC: 0.6728912
```
