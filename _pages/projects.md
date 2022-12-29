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

## Lung cancer prediction 

Lung cancer is a leading cause of cancer-related deaths worldwide. In this project, we aimed to predict the likelihood of an individual developing lung cancer using data on their smoking habits and other relevant factors.

To accomplish this goal, we started by collecting and selecting data from two sources: a dataset with around 150,000 lines (National Lung Screening Trial (NLST)) to use for training and a dataset with around 50,000 lines (Prostate, Lung, Colorectal and Ovarian (PLCO) Cancer Screening Trial) to use for testing. We then cleaned and prepared the data for use in our machine learning model.

Next, we used XGBoost, a powerful tool for building gradient boosting models, to train a machine learning model on the training dataset. We are currently in the process of evaluating the model's performance on the testing set using the area under the curve (AUC) metric, and using Shapley values to understand the specific factors that are driving the model's predictions.

Through this project, we hope to create a model that can accurately predict the likelihood of an individual developing lung cancer based on their smoking habits and other relevant data. This model could potentially be used to identify individuals at high risk for lung cancer and facilitate early detection and prevention efforts.

## Bird image classification 

As part of the class _Object Recognition and Computer Vision_ given by Ivan Laptev, Jean Ponce, Cordelia Schmid and Josef Sivic at ENS Paris Saclay, I participated in the "Bird image classification competition" on Kaggle, which involves building a neural network to recognize different breeds of birds from images.

To improve the performance of my model, I pursued three main strategies: improving and augmenting the dataset, using transfer learning with models trained on the ImageNet database, and modifying various parameters. These strategies included applying a set of data transformation techniques, such as a random horizontal flip, random rotation, and random affine transformation, as well as a ColorJitter to change the brightness and saturation of the images and a random crop transformation to remove part of the image. I also used a Mask-RCNN to detect birds in the images and crop them around the bird box.

In terms of transfer learning, I tried different models trained on the ImageNet database, including ResNet50, ResNet101, and ResNet152. The ResNet50 model was found to be the best solution, and I modified the parameters of the model such that they were frozen for the first 10 epochs and unfrozen for the last 10. I also used the Adam optimizer to improve the performance of the network.

Finally, I modified various parameters to improve the model, including the learning rate (set to 1E-4), the image size (set to 128), and the number of epochs (set to 20). I also implemented an early stop to prevent overfitting, causing the iterations to stop after 4 non-progressive iterations.

Overall, these efforts helped me to build an efficient model for classifying the images into the 20 different bird breeds. The results of these changes are summarized in the following table : 

| Modification | Avg Loss| Accuracy  |
| -------- | ------ | -----|
| Initial Net model | 0.0579 | 8/103 |
| ResNet50   | 0.0352 | 50/103 |
| +Image Augmentation | 0.0298 | 61/103 |
| +Weight freeze | 0.0253 | 67/103 |
| +Parameter changes | 0.0111 | 95/103 |
| +Bird cropping | 0.087 | 96/103 |

You can find more details on this project in the following python [Notebook](https://github.com/plbenveniste/plbenveniste.github.io/blob/a669c044c38d6a7044a9329dbfbec280dd3be878/f)
