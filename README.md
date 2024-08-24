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

dataset

## DINOv2

dinov2

## MambaVision

mambavision

## Results

table

## Prerequisites

## Prerequisites

Before using this project, ensure you have installed the following libraries and dependencies:

| Library                 | Version / Requirement                                                          |
|-------------------------|--------------------------------------------------------------------------------|
| Python                  | 3.5.5 or later                                                                 |
| torch                   | 2.1.2 or later (for some features: 2.0.0)                                      |
| torchvision             | 0.15.0                                                                         |
| causal-conv1d           | Latest (Check installation instructions)                                        |
| mamba-ssm               | Latest (Check installation instructions)                                        |
| timm                    | 0.9.2 or later                                                                 |
| tensorboardX            | 2.6 or later                                                                   |
| einops                  | 0.6.1 or later                                                                 |
| transformers            | 4.42.3 --extra-index-url https://download.pytorch.org/whl/cu117                 |
| omegaconf               | 2.3.0 or later                                                                 |
| torchmetrics            | 0.10.3                                                                         |
| fvcore                  | 0.1.5.post20221221 or later                                                    |
| iopath                  | 0.1.10 or later                                                                |
| xformers                | 0.0.18                                                                         |
| submitit                | 1.4.5 or later                                                                 |
| cuml-cu11               | Latest --extra-index-url https://pypi.nvidia.com                                |
| kornia                  | 0.7.3                                                                          |
| matplotlib              | 3.7.2                                                                          |
| numpy                   | 1.23.5                                                                         |
| pandas                  | 2.1.1                                                                          |
| seaborn                 | 0.13.0                                                                         |
| h5py                    | 3.10.0                                                                         |
| librosa                 | 0.10.2                                                                         |

## Usage

1. Clone the repository:

   !git clone https://github.com/Itamar-Horowitz/recaptcha-v2-decryptor.git

3. Navigate to the model folder:

   cd models

5. Run the desired model:

   XXX.ipynb

## References

