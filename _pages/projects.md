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


## Bird Image Classification

### Motivation

As part of the class _Object Recognition and Computer Vision_ given by Ivan Laptev, Jean Ponce, Cordelia Schmid and Josef Sivic at ENS Paris Saclay, I had to complete a bird image classification. The objective of this project was to code a Neural Network in order to classify birds amongst 20 breeds. 

In order to address this problem I focused on 3 strategies. I worked on these strategies independently in order to esti- mate the impact it had on the results of the classification. The strategies I looked at were the following ones :
 - I worked on improving the dataset and augmenting it.
 - I changed the model in order to profit from methods such as Transfer Learning.
 - Parameter modification can also have a significative impact on the results of the analysis.

### Methodology

Firstly, let’s describe data transformation and data augmenting. When modyfing the data I applied a set of data transformation on images in order to improve the performance of the model. In terms of data transformation I applied : a random horizontal flip, a random rotation, a random affine transformation. I also added a ColorJitter which changes the brightness and the saturation of the images, as well as a random crop transformation which removes part of the image. Finally, I used a Mask-RCNN in order to detect birds to be able to crop the pictures arount the bird box. This way, the following model will learn to recognize the birds without paying attention to the surrounding trees.

Than I worked on applying transfer learning with models trained on the ImageNet database. I tried different models to see if the results would be improved by working on deeper neural networks such as : ResNet50, ResNet101 and ResNet152. I compared the results given by the different networks for the same parameters and the ResNet50 appeared as the best solution. Then, during the training I changed the parameters of the model so that the parameters would be frozen for the first 10 epochs and then unfrozen for the last 10. Also, I changed the optimizer to an Adam optimizer.

Finally, changing some parameters also helped in order to improve the model. I changed the learning rate to a smaller one equal to $1E-4$. I changed the size of the images to 128 in order to retain more details from the images (I would have prefered to do it with 256 but it requires too much computation time). The number of epochs was also changed to 20 in order to get even closer to the solution. On the other hand, in order to counter the effects of a too high number of epochs, I added an early stop so that the iterations would stop after 4 non-progressive iterations.

### Results

In the following table we can see the evolution of the result with the sequential changes.

| Modification | Avg Loss| Accuracy  |
| -------- | ------ | -----|
| Initial Net model | 0.0579 | 8/103 |
| ResNet50   | 0.0352 | 50/103 |
| +Image Augmentation | 0.0298 | 61/103 |
| +Weight freeze | 0.0253 | 67/103 |
| +Parameter changes | 0.0111 | 95/103 |
| +Bird cropping | 0.087 | 96/103 |

You can find more details on this project in the following python [Notebook](/files/bird_classification_notebook.ipynb)

## Lung cancer prediction 

As part of a project with Paris' hospitals (Assistance Publique – Hôpitaux de Paris) I am currently working with Dr Jean-Emmanual Bibault. We are building a Machine Learning algorithm that predicts the chances that someone develops lung cancer based on their consumption of tobacco. We are using two databases : PLCO and NLST which group around 200 000 profiles and their data. The model is trained on the 150 000 lines of data of NLST and then tested on the 50 000 lines of PLCO. The dataset not only contains information on the person's tobacco consumption but also age, family, diseases and exposure to certain products.  

In order to compute the chances of someone developping lung cancer, we use XGBoost 


## Project 3 


