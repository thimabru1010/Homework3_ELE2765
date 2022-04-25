# Homework 3 ELE2765
Homework 3 of Deep Learning class on Electrical Engineering Master's at PUC-Rio

This Project has the objective of learning how a semantic segmentation network works, implementing more specifically U-Net, in a remote sensing dataset. The study idea is to train U-Net with **weighted cross entropy** loss, to handle class imbalance problem, and compare the result among dataset extracted with different patch sizes, since remote sensing images have a quite big resolution.

The number of pixels by class can be seen on the image below, to show clerly the imabalance problem:

<p align="center">
  <img src="classes.png" alt="Number of pixels by class"/>
</p>


