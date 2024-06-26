---
layout: archive
permalink: /projects/
excerpt: "Projects"
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

# Research Projects
------

{::comment}

## Object Tracking using DiffusionDet (current project)
******** 


Traditional object detection methods rely on annotated datasets to learn the appearance and location of objects in images or videos. However, these methods can be limited in their ability to generalize to new environments and conditions. To address this issue, the DiffusionDet article proposes a new approach to object detection using diffusion models. Diffusion models have previously been used in image processing and pattern recognition, but have not been widely explored for object detection. In this study, we aimed to understand the DiffusionDet method and its potential for object detection and tracking.

To understand the DiffusionDet method, we first examined the mathematics behind the diffusion process and how it can be used to add noise to the ground truth bounding boxes. We then implemented the code from the DiffusionDet GitHub repository and applied it to the MOT17 dataset for object tracking. This allowed us to evaluate the performance of the DiffusionDet method in a real-world setting and compare it to other object detection approaches.

Our results so far suggest that the DiffusionDet method can improve the robustness and generalizability of object detection models by introducing variability and uncertainty in the training data. When applied to the MOT17 dataset for object tracking, the DiffusionDet method demonstrated promising performance, with a high average precision and a low miss rate. However, we are still in the process of evaluating the DiffusionDet method and do not yet have clear conclusions.

The code will be added at a later date.

{:/comment}
{::comment}
## Exploring latent spaces of Deep Generative Models
**********

In this project, I discuss the paper "Latent Space Oddity: On the curvature of deep generative models," which aims to understand the geometric structure of latent spaces in generative models and how it can be used to improve model performance. Generative models are used to generate new data samples that are similar to a training dataset and have a wide range of applications. The latent space is a lower-dimensional representation of the input data that captures the underlying structure and patterns of the data. To better understand the curvature of latent spaces and improve the performance of deep generative models, the authors propose a new stochastic Riemannian metric and a new variance network for the generator. The potential applications of this work are broad, as most tasks involving variables in a latent space, such as classification or clustering using VAEs or image translation with GANs, would benefit from a more accurate metric to measure distances in latent spaces. 

We are currently working on comparing the results of the authors' approach with the application of a VAE model on the CIFAR-10 dataset. The authors demonstrate the benefits of their approach through several experiments, including comparing the performance of the Riemannian metric to Euclidean metrics for computing distances and for interpolation tasks, using a locally adaptive normal distribution (LAND) for sampling in the latent space, and performing a random walk on the latent space of a generative model. The variance network is based on a Radial Basis Function (RBF) network and helps to overcome the poor extrapolation performance of neural networks when estimating variance. Overall, the use of the Riemannian metric and the variance network helps to improve the performance of generative models by better capturing the curvature and structure of the latent space.

For more details, here is the project [report](https://github.com/plbenveniste/plbenveniste.github.io/blob/master/files/Latent_space_oddity_Project_report.pdf)

The code will be added at a later date.
{:/comment}
{::comment}
## Bird image classification 
********

As part of the class _Object Recognition and Computer Vision_, given by Ivan Laptev, Jean Ponce, Cordelia Schmid and Josef Sivic, at ENS Paris Saclay, I participated in the "Bird image classification competition" on Kaggle, which involves building a neural network to recognize different breeds of birds from images.

To improve the performance of my model, I pursued three main strategies: improving and augmenting the dataset, using transfer learning with models trained on the ImageNet database, and modifying various parameters. These strategies included applying a set of data transformation techniques, such as a random horizontal flip, random rotation, and random affine transformation, as well as a ColorJitter to change the brightness and saturation of the images and a random crop transformation to remove part of the image. I also used a Mask-RCNN to detect birds in the images and crop them around the bird box.

In terms of transfer learning, I tried different models trained on the ImageNet database, including ResNet50, ResNet101, and ResNet152. The ResNet50 model was found to be the best solution, and I modified the parameters of the model such that they were frozen for the first 10 epochs and unfrozen for the last 10. I also used the Adam optimizer to improve the performance of the network.

Finally, I modified various parameters to improve the model, including the learning rate (set to 1E-4), the image size (set to 128), and the number of epochs (set to 20). I also implemented an early stop to prevent overfitting, causing the iterations to stop after 4 non-progressive iterations.

Overall, these efforts helped me to build an efficient model for classifying the images into 20 different bird breeds. The results of these changes are summarized in the following table : 

| Modification | Avg Loss| Accuracy  |
| -------- | ------ | -----|
| Initial Net model | 0.0579 | 8/103 |
| ResNet50   | 0.0352 | 50/103 |
| +Image Augmentation | 0.0298 | 61/103 |
| +Weight freeze | 0.0253 | 67/103 |
| +Parameter changes | 0.0111 | 95/103 |
| +Bird cropping | 0.087 | 96/103 |


You can find more details on this project in the following python [Notebook](https://github.com/plbenveniste/plbenveniste.github.io/blob/a669c044c38d6a7044a9329dbfbec280dd3be878/files/bird_classification_notebook.ipynb)
{:/comment}
