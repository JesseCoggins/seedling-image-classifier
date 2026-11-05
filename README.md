# Identifying plant seedlings from images

I trained a convolutional neural network to distinguish **12 seedling species** from photographs. It classified **66.62% of 713 held-out images** correctly. For a botanist sorting images of crops and weeds, the class-by-class results matter more than a single accuracy figure. The model recognized Common wheat much more reliably than Shepherd’s Purse.

[Inspect the training and evaluation notebook](notebooks/seedling_cnn_classifier.ipynb) · [Download the trained Keras model](models/seedling_classifier_model.keras) · [Set up the training images](data/README.md)

## Results

| Species | Test F1 score |
|---|---:|
| Common Chickweed | 0.83 |
| Common wheat | 0.83 |
| Scentless Mayweed | 0.56 |
| Fat Hen | 0.50 |
| Shepherd’s Purse | 0.42 |

F1 summarizes how often a species label is correct and how often the classifier finds that species. The results support trying a first-pass sorting workflow with expert review for easily confused seedlings. A field evaluation would be needed before using the labels to guide treatment. The notebook includes a confusion matrix and scores for all 12 classes. [Figures from the project report](assets/report-extracts/)

## How I built it

- Normalized 4,750 RGB images of 128 × 128 pixels and stratified the split into 3,325 training, 712 validation and 713 test images.
- Used two convolution and max-pooling blocks, a 128-unit dense layer with dropout, and a 12-class softmax output.
- Trained with image augmentation and class weights. Early stopping monitored validation loss and restored the best weights. The notebook calculates class weights from the full label distribution.

## Inspect or retrain

The saved model and [class names in output order](data/class_names.csv) are included. For a quick inspection, run this from the repository root in a Python environment with the [requirements](requirements.txt) installed.

~~~python
from tensorflow.keras.models import load_model

model = load_model("models/seedling_classifier_model.keras", compile=False)
model.summary()
~~~

To retrain, follow the [download and checksum instructions](data/README.md) for the matching 223 MiB image array. Place it next to the included labels and run the notebook with `notebooks/` as the working directory.

## Data and environment

Data: Aarhus seedling images used in the WGU project; [download and attribution](data/README.md).  
Install: `python -m pip install -r requirements.txt`; [environment details](requirements-verified.txt).

*WGU M.S. in Data Analytics coursework, D604 Advanced Analytics.*
