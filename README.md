# Deep Learning Pipeline for Lung Cancer CT Classification

This repository contains the complete workflow, implementation, and report for a deep learning project focused on automatic lung cancer malignancy classification from computed tomography (CT) images.

The project implements and evaluates four convolutional neural network (CNN) classifiers:
- Full-slice binary classification (benign vs. malignant)
- Full-slice five-class malignancy scoring
- Nodule-crop binary classification
- Nodule-crop five-class malignancy scoring

## Overview

Lung cancer is one of the leading causes of cancer-related deaths. Accurate malignancy scoring from CT scans can support radiologists and improve diagnostic efficiency. This project explores how transfer learning and modern CNN architectures can be applied to this problem on a small, imbalanced dataset.

## Features

- Data preprocessing: Hounsfield unit clipping, zero-padding, resizing, normalization
- Outlier detection using pretrained feature extractors and t-SNE visualization
- Dataset splitting with stratification and evaluation metric design (weighted AUPRC, F1)
- Backbone selection through feature extractor screening
- Class imbalance mitigation with augmentation-based upsampling
- Hyperparameter optimization: batch size, optimizer, classifier head design
- Final model fine-tuning with various unfreezing schedules
- Explainability with Grad-CAM++

## Results

| Model              | Dataset     | Task        | Weighted AUPRC |
|--------------------|-------------|-------------|----------------|
| ConvNeXt-Tiny      | Nodule      | Binary      | 0.88           |
| ConvNeXt-Tiny      | Full Slice  | Binary      | 0.81           |
| ConvNeXt-Tiny      | Nodule      | 5-Class     | 0.55           |
| ConvNeXt-Tiny      | Full Slice  | 5-Class     | 0.41           |

## Explainability

Grad-CAM++ visualizations demonstrate that the models attend to clinically relevant regions such as nodules and surrounding tissue, improving interpretability and trustworthiness.

## Future Work

- Pretraining on medical-domain CT datasets
- Expanded augmentation hyperparameter search
- Cross-validation to evaluate embedding robustness
- Retraining with the full dataset after tuning

## Authors

- M. Alipoor  
- S. N. Ghareghani  
- M. Tirabassi
