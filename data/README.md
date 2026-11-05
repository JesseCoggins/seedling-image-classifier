# Training images and labels

The notebook uses 4,750 seedling images in 12 classes. The repository includes the row-aligned labels and trained Keras model. For a full training run, download the matching NumPy array from the [archived dataset on Zenodo](https://zenodo.org/records/17586748). The archive’s published MD5 matches the image array used in this coursework.

From the repository root, download the array into the directory that already contains the labels:

~~~shell
curl --fail --location "https://zenodo.org/records/17586748/files/images.npy?download=1" --output data/seedling_dataset/images.npy
~~~

| File | Size or shape | Checksum of original file |
|---|---|---|
| `images.npy` | 233,472,128 bytes, shape (4,750, 128, 128, 3), uint8 | SHA-256 `101f6827918a57f8758c37e30523938e1330556366ac8e393259216575b04b08` |
| `labels.csv` | 4,750 labels in image order | Original MD5 `70ee9b0f7f0b8f586bda591531fd1ca6` |

Git may convert the CSV’s line endings on checkout. Preserve its row order. Open [the training notebook](../notebooks/seedling_cnn_classifier.ipynb) with its working directory set to `notebooks/`. To inspect the model without retraining, use the [saved Keras model](../models/seedling_classifier_model.keras).

## Original source and attribution

The underlying images are from the [Aarhus Plant Seedlings Dataset](https://vision.eng.au.dk/plant-seedlings-dataset/), recorded at Aarhus University Flakkebjerg Research Station with the University of Southern Denmark. Copyright © 2014 Mads Dyrmann, Peter Christiansen, University of Southern Denmark, and Aarhus University. The source page links [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) for images and annotations and requires citation for trained models and other derived work.

Giselsson, T. M., Jørgensen, R. N., Jensen, P. K., Dyrmann, M., and Midtiby, H. S. (2017). *A Public Image Database for Benchmark of Plant Seedling Classification Algorithms*. [arXiv:1711.05458](https://arxiv.org/abs/1711.05458).

The course input is a resized 128 × 128 NumPy image array and aligned labels. The Zenodo record above is a matching download mirror, not the original dataset creator. The notebook normalizes images, augments training samples and trains the included model; it does not claim ownership of the original photographs. License scope is documented separately for each artifact:

| Artifact | License |
|---|---|
| Project code | [MIT](../LICENSE) |
| Source images and annotations | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/), with the source attribution above |
| Included trained model | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/), as stated in the [model notes](../models/README.md) |
