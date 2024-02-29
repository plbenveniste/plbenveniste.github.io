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


## Multiple Sclerosis (MS) lesion segmentation in the Spinal Cord (SC)
********

**Motivation:** Longitudinal analysis of spinal cord multiple sclerosis (MS) lesions is clinically relevant for the early diagnosis and monitoring of MS progression. 

**Goal(s):** Develop a deep learning tool for the automatic segmentation of MS spinal cord lesions on PSIR and STIR images from multiple sites.

**Data:** 3T MRI, cervical spinal cord, sagittal (0.7×0.7×3 mm3) PSIR (4 sites, 333 participants) and STIR (1 site, 92 participants) images.

**Approach:** A nnUNet model was trained and tested on the baseline data and applied to follow-up scans to create lesion distribution maps.

**Results:** We demonstrated the utility of the model to map the spatio-temporal distribution of MS lesions across MS phenotypes. The model is packaged into an open-source software. 

Here is the poster I am presenting at ACTRIMS regarding this work: [poster_actrims_2024](https://github.com/plbenveniste/plbenveniste.github.io/blob/master/files/poster_actrims_2024.pdf)


## Lung cancer prediction 
********

**Abstract**

Introduction: Lung cancer is a significant cause of mortality worldwide, emphasizing the importance of early detection for improved survival rates. In this study, we propose a machine learning (ML) tool trained on data from the PLCO Cancer Screening Trial and validated on the NLST to estimate the risk of lung cancer occurrence within five years.

Methods: The study utilized two datasets, the PLCO (n=55,161) and NLST (n=48,595), consisting of comprehensive information on risk factors, clinical measurements, and outcomes related to lung cancer. Data preprocessing involved removing patients who were not current or former smokers and those who had died of causes unrelated to lung cancer. Additionally, we focused on mitigating bias caused by censored data. Feature selection, hyperparameter optimization, and model calibration were performed using XGBoost, an ensemble learning algorithm that combines gradient boosting and decision trees.

Results: The ML model was trained on the preprocessed PLCO dataset and tested on the NLST dataset. It incorporated features such as age, smoking history, medical diagnoses, and family history of lung cancer. The model was well-calibrated (Brier score = 0.044). ROC-AUC was 82% on the PLCO dataset and 70% on the NLST dataset. PR-AUC was 29% and 11% respectively. When compared to the USPSTF guidelines for lung cancer screening, our model provided the same recall with a precision of 13.1% vs. 9.3% on the PLCO dataset and 3.2% vs. 3.1% on the NLST dataset.

Conclusion: We developed a web application that provides this ML model to estimate the risk of lung cancer within five years. Using risk factors and clinical data, individuals can assess their risk and make informed decisions regarding lung cancer screening. This research contributes to the efforts in early detection and prevention strategies, aiming to reduce lung cancer-related mortality rates.

**Preprint**: [https://doi.org/10.48550/arXiv.2308.12188](https://doi.org/10.48550/arXiv.2308.12188)

**Code**: [GitHub repo](https://github.com/plbenveniste/LungCancerRisk)

**Prediction tool**: [App link](https://lung-cancer-risk-7f6ac1f97fd0.herokuapp.com/)


## Exploring latent spaces of Deep Generative Models
**********

In this project, I discuss the paper "Latent Space Oddity: On the curvature of deep generative models," which aims to understand the geometric structure of latent spaces in generative models and how it can be used to improve model performance. Generative models are used to generate new data samples that are similar to a training dataset and have a wide range of applications. The latent space is a lower-dimensional representation of the input data that captures the underlying structure and patterns of the data. To better understand the curvature of latent spaces and improve the performance of deep generative models, the authors propose a new stochastic Riemannian metric and a new variance network for the generator. The potential applications of this work are broad, as most tasks involving variables in a latent space, such as classification or clustering using VAEs or image translation with GANs, would benefit from a more accurate metric to measure distances in latent spaces. 

We are currently working on comparing the results of the authors' approach with the application of a VAE model on the CIFAR-10 dataset. The authors demonstrate the benefits of their approach through several experiments, including comparing the performance of the Riemannian metric to Euclidean metrics for computing distances and for interpolation tasks, using a locally adaptive normal distribution (LAND) for sampling in the latent space, and performing a random walk on the latent space of a generative model. The variance network is based on a Radial Basis Function (RBF) network and helps to overcome the poor extrapolation performance of neural networks when estimating variance. Overall, the use of the Riemannian metric and the variance network helps to improve the performance of generative models by better capturing the curvature and structure of the latent space.

For more details, here is the project [report](https://github.com/plbenveniste/plbenveniste.github.io/blob/master/files/Latent_space_oddity_Project_report.pdf)

