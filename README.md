# ReCAPTCHA V2 decryption with DINOv2 and MambaVision 

<p align="center">
  <img width="500" src="https://github.com/Itamar-Horowitz/recaptcha-v2-decryptor/blob/main/images/google_recaptcha.png">
</p>

## Table of Contents
  * [Abstract](#background)
  * [Dataset](#dataset)
  * [DINOv2](#dinov2)
  * [MambaVision](#mambavision)
  * [Results](#results)
  * [Prerequisites](#prerequisites)
  * [Quick start](#quickstart)
  * [References](#references)

## Abstract

The ability to protect websites from various automated attacks is crucial for businesses, governments, and any other entities with websites containing sensitive data. ReCAPTCHA serves as a security measure to defend against these malicious threats. Our project aims to solve the puzzles posed by ReCAPTCHA v2 by applying advanced machine learning techniques. Specifically, we explore the effectiveness of transfer learning with MambaVision and compare it with the DINOv2 model, which does not rely on transfer learning. Our analysis reveals that DINOv2 outperforms MambaVision and other models in solving ReCAPTCHA v2 challenges, demonstrating its capability to produce robust, high-performance visual features for computer vision tasks without the need for transfer learning.

## Dataset

The dataset used was taken from Kaggle, containing 40,022 images across 11 different categories. The dataset was split into 70% for training, and 15% each for validation and testing. Additionally, normalization procedures were applied to the features, and images were scaled to 100x100 pixels.

Here is a glance at our dataset:

| Class          | Train | Validation | Test | Total |
|----------------|-------|------------|------|-------|
| Bicycle        | 1705  | 365        | 366  | 2436  |
| Bridge         | 1267  | 271        | 273  | 1811  |
| Bus            | 5862  | 1256       | 1257 | 8375  |
| Car            | 6776  | 1452       | 1453 | 9681  |
| Chimney        | 272   | 58         | 59   | 389   |
| Crosswalk      | 2307  | 494        | 495  | 3296  |
| Hydrant        | 4872  | 1044       | 1045 | 6961  |
| Motorcycle     | 193   | 41         | 43   | 277   |
| Palm           | 1791  | 383        | 385  | 2559  |
| Stair          | 450   | 96         | 98   | 644   |
| Traffic Light  | 2515  | 538        | 540  | 3593  |
| **Total**      | 28010 | 5998       | 6014 | 40022 |

## DINOv2

DINOv2 is a self-supervised learning framework that builds on the original DINO (Distillation with No Labels) approach, leveraging Vision Transformers (ViTs) to extract meaningful features from images without requiring labeled data. The key innovations of DINOv2 include multi-crop training, which allows the model to handle images at various resolutions, and momentum encoders, which help the model maintain stable representations across training iterations. By focusing on these methods, DINOv2 is able to outperform traditional convolutional networks and supervised transformers in tasks such as image classification, object detection, and segmentation.

Additionally, DINOv2 uses a contrastive learning technique to distinguish between similar and dissimilar images in the feature space, which enhances its ability to categorize images accurately. With its powerful self-distillation process, DINOv2 can generate rich visual representations, making it highly effective for complex vision tasks.

## MambaVision

MambaVision is a cutting-edge model that employs a combination of self-attention mechanisms and mixer blocks to process visual data. It introduces an innovative selective scan algorithm, which filters out irrelevant information, along with a hardware-aware algorithm to optimize memory and processing performance. Unlike DINOv2, MambaVision relies on transfer learning to adapt pre-trained models for specific tasks, which can make it more suitable for cases where fine-tuning on smaller datasets is necessary.

One of MambaVision's core strengths is its ability to model global contexts in images, thanks to its hierarchical structure and selective SSM (State-Space Model). The architecture includes a mix of self-attention paths and convolutional layers, creating a flexible model capable of handling complex visual tasks.

## Results

The table below summarizes the performance of the models used in this project:

| Model        | Technique                      | Test Accuracy |
|--------------|--------------------------------|---------------|
| DINOv2       | Hyperparameters tuning (Optuna) | 95.9%         |
| MambaVision  | Fine-tuning (DoRA)             | 83.8%         |
| ResNet18     | Fine-tuning (DoRA)             | 77.8%         |

The results clearly show that DINOv2 is the most effective model for solving ReCAPTCHA challenges, even without using transfer learning. Its ability to process unlabeled data and generate rich visual representations allows it to surpass MambaVision and ResNet18 in accuracy. While MambaVision showed solid performance, it required more fine-tuning and was more sensitive to low-quality data compared to DINOv2.

## Prerequisites

Before using this project, ensure you have installed the following libraries and dependencies:

| Library                 | Version               |
|-------------------------|-----------------------|
| Python                  | 3.5.5 or later        |
| torch                   | 2.1.2 or later        |
| torchvision             | 0.15.0                |
| causal-conv1d           | 1.4.0                 |
| mamba-ssm               | 2.2.2                 |
| timm                    | 0.9.2 or later        |
| tensorboardX            | 2.6 or later          |
| einops                  | 0.6.1 or later        |
| transformers            | 4.42.3                |
| torchmetrics            | 0.10.3                |
| kornia                  | 0.7.3                 |
| matplotlib              | 3.7.2                 |
| numpy                   | 1.23.5                |
| pandas                  | 2.1.1                 |
| seaborn                 | 0.13.0                |
| h5py                    | 3.10.0                |
| librosa                 | 0.10.2                |

## Quick start

1. Clone the repository:
   ```bash
   git clone https://github.com/Itamar-Horowitz/recaptcha-v2-decryptor.git

2. Navigate to the models folder:
   ```bash
   cd ./models

3. Run the desired model (example):
   ```bash
   jupyter notebook DINOv2Model.ipynb

## References

- MambaVision: [https://github.com/NVlabs/MambaVision](https://github.com/NVlabs/MambaVision)
- DINOv2: [https://github.com/facebookresearch/dinov2](https://github.com/facebookresearch/dinov2)
- Cracking ReCAPTCHA with CNNs: [https://medium.com/analytics-vidhya/cracking-recaptchas-with-cnns-and-transfer-learning-edc26ab675ec](https://medium.com/analytics-vidhya/cracking-recaptchas-with-cnns-and-transfer-learning-edc26ab675ec)

