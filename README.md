# Seedling Image Classifier

## Overview
This project applies deep learning to a computer vision classification task involving plant seedlings. The notebook covers image preprocessing, model training, and evaluation for a multi-class image classification problem.

This staged version is set up so the trained CNN artifact is included for inference and inspection, while the oversized raw training array is documented separately rather than committed directly.

## Coursework Context
This repository packages work originally completed as part of Western Governors University's (WGU) M.S. in Data Analytics program and reorganizes it into a public portfolio format. Screenshots extracted from the original written submission are preserved in `assets/report-extracts/`.

## What It Shows
- image preprocessing for a CNN workflow
- supervised multi-class classification
- TensorFlow/Keras deep learning workflow
- model evaluation and class labeling

## Included Files
- `notebooks/Task-1.ipynb`
- `data/class_names.csv`
- `data/39af014a165dbbdd9d14eaadbab26cda/labels.csv`
- `data/README.md`
- `models/seedling_classifier_model.keras`
- `models/README.md`
- `requirements.txt`

## What Works Out Of The Box
- model architecture review in the notebook
- access to class labels and label metadata
- loading the trained `.keras` model for inference-oriented inspection

## Remaining Limitation
- the original `images.npy` training array is about 223 MB and exceeds normal GitHub limits, so it is not included in this repo

## Note
This repo follows a hybrid portfolio approach:
- include the trained model so reviewers can inspect or load it
- document the missing training array transparently in `data/README.md`

## Suggested Next Additions
- training and validation curves
- confusion matrix
- sample predictions
- a few representative images for each class
