# ReCAPTCHA V2 decryption using DINOv2 and MambaVision 

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
  * [Usage](#usage)
  * [References](#references)

## Abstract
Ensuring the security of online platforms against automated attacks is essential for protecting sensitive data on websites. ReCAPTCHA v2, developed by Google, is widely used to differentiate human users from bots and defend against various malicious activities. This report examines the performance of ReCAPTCHA v2 by applying advanced machine learning techniques. Specifically, we explore the effectiveness of transfer learning with MambaVision and compare it with the DINOv2 model, which does not use transfer learning. Our analysis reveals that DINOv2 outperforms MambaVision and other models in solving ReCAPTCHA V2 challenges, demonstrating its potential to significantly enhance ReCAPTCHA’s security capabilities.

## Dataset

The dataset used was taken from Kaggle, containing 40,022 images across 11 different categories. The dataset was split into 70% for training, and 15% each for validation and testing. Additionally, normalization procedures were applied to the features, and images were scaled to 100x100 pixels.

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

dinov2

## MambaVision

mambavision

## Results

The table below summarizes the performance of the models used in this project:

| Model        | Technique | Test Accuracy |
|--------------|-----------|---------------|
| ResNet       | DoRA      | 77.2%         |
| MambaVision  | DoRA      | 81.9%         |
| DINOv2       | Optuna    | 96.1%         |

The chart below shows the training and validation accuracy for each epoch:

<p align="center">
  <img width="500" src="path_to_chart_image">
</p>

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

## Usage


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

