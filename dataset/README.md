# Feature Extraction from Handwritten Digits

## Project Overview

This project focuses on extracting meaningful features from handwritten digit images and analyzing different feature representations.

The project uses 1,584 handwritten digit images of the digit **0**. The images are preprocessed and converted into numerical feature representations using different techniques.

## Objectives

* Load and preprocess handwritten digit images.
* Normalize image pixel values.
* Extract HOG (Histogram of Oriented Gradients) features.
* Represent images using raw pixel features.
* Apply PCA for dimensionality reduction.
* Compare different feature representations.
* Visualize the extracted features and PCA results.

## Dataset

The dataset contains **1,584 images** of handwritten digit `0`.

Image dimensions:

* 28 × 28 pixels
* PNG format
* RGBA images

The handwritten information is stored in the alpha channel of the images.

## Methodology

```text
Handwritten Images
        ↓
Image Loading
        ↓
Alpha Channel Extraction
        ↓
Grayscale Image Representation
        ↓
Normalization
        ↓
Feature Extraction
   ┌──────────────┬──────────────┐
   ↓              ↓              ↓
Raw Pixels       HOG            PCA
   ↓              ↓              ↓
Feature Analysis & Visualization
```

## Feature Extraction Techniques

### 1. Raw Pixel Features

Each 28 × 28 image is flattened into a one-dimensional feature vector.

**784 features per image**

### 2. HOG Features

Histogram of Oriented Gradients extracts information about the edges, gradients, and shape of the handwritten digit.

**1,296 features per image**

### 3. PCA

Principal Component Analysis reduces the dimensionality of the raw pixel features while preserving approximately 95% of the variance.

**97 PCA features**

## Results

| Feature Method | Number of Features |
| -------------- | -----------------: |
| Raw Pixels     |                784 |
| HOG            |              1,296 |
| PCA            |                 97 |

PCA reduced the feature representation from **784 dimensions to 97 dimensions** while retaining approximately 95% of the variance.

## Project Structure

```text
Feature Extraction from Handwritten Digits/
│
├── dataset/
│   └── 0/
│       └── 0/
│           └── handwritten images
│
├── notebooks/
│   └── 01_data_preprocessing.ipynb
│
├── results/
│   ├── hog_features.npy
│   ├── pca_features.npy
│   ├── pca_visualization.png
│   ├── hog_visualization.png
│   ├── feature_comparison.csv
│   ├── final_feature_summary.csv
│   └── feature_dimension_comparison.png
│
├── src/
│
└── README.md
```

## Technologies Used

* Python
* NumPy
* Pandas
* OpenCV
* Pillow
* Matplotlib
* Scikit-image
* Scikit-learn
* Jupyter Notebook

## Conclusion

The project demonstrates how handwritten digit images can be transformed into meaningful numerical representations.

HOG captures shape and edge information, while PCA provides an effective way to reduce feature dimensionality. The comparison demonstrates that dimensionality reduction can significantly reduce the number of features while preserving most of the information present in the original data.

## Future Scope

* Extend the dataset to include digits 0–9.
* Train machine learning classifiers using the extracted features.
* Compare classification accuracy using Raw Pixel, HOG, and PCA features.
* Experiment with additional feature extraction techniques such as LBP and Gabor features.
* Develop a user interface for handwritten digit recognition.
