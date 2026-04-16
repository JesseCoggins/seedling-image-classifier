# Seedling Image Classifier

## Overview
This project applies deep learning to a computer vision classification task involving plant seedlings. The notebook covers image preprocessing, model training, and evaluation for a multi-class image classification problem.

The trained model artifact is included so it can be loaded or inspected without retraining. The raw image training array (~223 MB) exceeds GitHub's file size limits and isn't included — that's documented in `data/README.md`.

## Coursework Context
This project was completed as part of my M.S. in Data Analytics program at Western Governors University (WGU). Screenshots from the original written submission are preserved in `assets/report-extracts/`.

## What It Shows
- image preprocessing for a CNN workflow
- supervised multi-class classification
- TensorFlow/Keras deep learning workflow
- model evaluation and class labeling

## Included Files
- `notebooks/seedling_cnn_classifier.ipynb`
- `data/class_names.csv`
- `data/seedling_dataset/labels.csv`
- `data/README.md`
- `models/seedling_classifier_model.keras`
- `models/README.md`
- `requirements.txt`

## What Works Out Of The Box
- model architecture review in the notebook
- access to class labels and label metadata
- loading the trained `.keras` model for inference-oriented inspection

## Results

- The trained CNN achieved test accuracy of `0.6662` (`66.62%`) across `12` plant seedling classes.
- Class-level performance was strongest on Common Chickweed (`0.83` F1) and Common wheat (`0.83` F1).
- More visually similar species such as Shepherd's Purse (`0.42` F1), Fat Hen (`0.50` F1), and Scentless Mayweed (`0.56` F1) remained more challenging, which is typical in fine-grained image classification.

## Selected Visuals

![Seedling report visual 1](assets/report-extracts/report_image_01.png)

![Seedling report visual 2](assets/report-extracts/report_image_02.png)

## Remaining Limitation
- the original `images.npy` training array is about 223 MB and exceeds normal GitHub limits, so it is not included in this repo

## Note
This repo follows a hybrid portfolio approach:
- include the trained model so reviewers can inspect or load it
- document the missing training array transparently in `data/README.md`
