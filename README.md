# Homework 3 ELE2765
Homework 3 of Deep Learning class on Electrical Engineering Master's at PUC-Rio

## Introduction

This Project has the objective of learning how a semantic segmentation network works, implementing more specifically U-Net, in a remote sensing dataset. As long as the dataset has a huge imabalance problem we used **weighted cross entropy** loss, which is also implemented in tensorflow 2.x (keras), to handle class imbalance problem. The idea of the project is to compare the results among different trails of the same dataset extracted with different patch sizes, since remote sensing images have a quite big resolution and see how the patch size affects the performance of the network.

The number of pixels by class can be seen on the image below, to show clearly the imabalance problem:

<p align="center">
  <img width="651" height="157" src="classes.png" alt="Number of pixels by class"/>
</p>

The weights calculation of each class for the loss function can be seen below:

<p align="center">
  <img width="267" height="56" src="class_weights.png" alt="Class weights for loss function"/>
</p>

If this weight calculation doesn't fit for you, you can try a normalized version (the sum of all classes are equal to 1).

## Training
inside the notebook `train_model.ipynb` you have all the necessary scripts to train U-Net, including U-Net architecture implementation, patches extraction, **weighted cross entropy** custom loss and more.

I used a stride with half the size of patch size, to enhance the the size of training data, since I had only one image to train. Also, if you have a powerful GPU, use a bigger patch size.

The model hyperparameters of the three trials, can be seen below:
<p align="center">
  <img src="models_parameters.png" alt="Number of pixels by class"/>
</p>

If you want to reproduce results the dataset is in this drive: https://drive.google.com/drive/folders/17sy0-ljxP9xQH8ANvjsZTru8aCOxZz4x?usp=sharing

## Testing
On testing notebook `Test_model.ipynb` you have all the preprocess scripts and also prediction patches reconstruction and patches visualization code.

## Results

### Model histories
We can see an intresting observation in model training histories. As long as we reduce the patch size more noisy is the training:

<p align="center">
  <img src="LateX_images/history_model1.png" alt="Model 1 history"/>
</p>

<p align="center">
  <img src="LateX_images/history_model2.png" alt="Model 2 history"/>
</p>

<p align="center">
  <img src="LateX_images/history_model3.png" alt="Model 3 history"/>
</p>

### Model metrics
Also, looking into the metrics we can see model 1, with the greater patch size, is the best model.

<p align="center">
  <img src="LateX_images/metrics_model1.png" alt="Model 1 metrics"/>
</p>

<p align="center">
  <img src="LateX_images/metrics_model2.png" alt="Model 2 metrics"/>
</p>

<p align="center">
  <img src="LateX_images/metrics_model3.png" alt="Model 3 metrics"/>
</p>

### Predictions reconstruction

<p align="center">
  <img width="352" height="319" src="LateX_images/Reference_Test.jpeg" alt="reference test image"/>
</p>

<p align = "center">
<strong>
Test reference
</strong>
</p>

<p align="center">
  <img width="352" height="319" src="LateX_images/img_reconstructed_rgb_model1.jpeg" alt="Model 1 pred reconstruction"/>
</p>

<p align = "center">
<strong>
Model 1 prediction reconstruction
</strong>
</p>

<p align="center">
  <img width="352" height="319" src="LateX_images/img_reconstructed_rgb_model2.jpeg" alt="Model 2 pred reconstruction"/>
</p>

<p align = "center">
<strong>
Model 2 prediction reconstruction
</strong>
</p>

<p align="center">
  <img width="352" height="319" src="LateX_images/img_reconstructed_rgb_model3.jpeg" alt="Model 3 pred reconstruction"/>
</p>

<p align = "center">
<strong>
Model 3 prediction reconstruction
</strong>
</p>
