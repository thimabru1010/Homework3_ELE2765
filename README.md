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


## Results

The model hyperparameters of the three trials, can be seen below:
<p align="center">
  <img src="models_parameters.png" alt="Number of pixels by class"/>
</p>

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

### Model prediction reconstruction
Comparing the reconstructed prediction of each model with the test reference we can see more mispredictions, specifically of class 2 for models 2 and 3.

<p align="center">
  <img width="704" height="639" src="LateX_images/Reference_Test.jpeg" alt="reference test image"/>
</p>

<p align="center">
  <img width="704" height="639" src="LateX_images/img_reconstructed_rgb_model1.jpeg" alt="Model 1 pred reconstruction"/>
</p>

<p align="center">
  <img width="704" height="639" src="LateX_images/img_reconstructed_rgb_model2.jpeg" alt="Model 2 pred reconstruction"/>
</p>

<p align="center">
  <img width="704" height="639" src="LateX_images/img_reconstructed_rgb_model3.jpeg" alt="Model 3 pred reconstruction"/>
</p>
