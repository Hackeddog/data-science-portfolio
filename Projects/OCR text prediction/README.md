# OCR Text Prediction

This project is an Optical Character Recognition (OCR) image classification model that predicts what letter or character is shown in an image. The model learns from labeled character images and classifies each input image into the correct character class.

## Project Overview

The goal of this project is to build a machine learning model that can recognize handwritten or printed characters from image data. It uses a Convolutional Neural Network (CNN) trained on an OCR dataset containing character images.

The notebook covers the full workflow:

- Loading an OCR dataset from Kaggle
- Exploring the image folders and class labels
- Checking image size, brightness, and class distribution
- Preprocessing images into grayscale
- Resizing images to `28x28` pixels
- Normalizing pixel values
- Training a CNN classification model
- Evaluating model accuracy, precision, recall, and loss
- Visualizing training history and confusion matrix
- Predicting letters from sample test images

## Dataset

The project uses the **Standard OCR Dataset** from Kaggle.

Dataset source used in the notebook:

```python
kagglehub.dataset_download("preatcher/standard-ocr-dataset")
```

The dataset contains folders for different character classes. Each folder represents a specific letter, digit, or symbol class. The images are organized into training and testing directories.

## Model Description

The OCR model is built using TensorFlow/Keras with a CNN architecture.

Main model layers include:

- `Conv2D` layers for feature extraction
- `BatchNormalization` for stable training
- `MaxPooling2D` for reducing image dimensions
- `Flatten` layer for converting feature maps
- `Dense` layer for classification
- `Dropout` to reduce overfitting
- `Softmax` output layer for multi-class prediction

The model predicts among **36 classes**, representing:

- 10 digits: `0-9`
- 26 letters: `A-Z`

## Performance

During training, the model reached a peak training accuracy of approximately **97.68%**. The notebook also evaluates the model using:

- Accuracy
- Precision
- Recall
- Test loss
- Confusion matrix

## Files

| File | Description |
|---|---|
| `OCR_LAMSIN_CORPUZ_SULIT.ipynb` | Main Jupyter notebook containing the OCR workflow, model training, evaluation, and prediction examples. |
| `OCR_dataset.zip` | OCR dataset file used for training/testing. |

## How It Works

1. Images are loaded from the OCR dataset.
2. Each image is converted to grayscale.
3. Images are resized to `28x28` pixels.
4. Pixel values are normalized between `0` and `1`.
5. The CNN model learns character patterns from the training data.
6. The trained model predicts the character class of new image inputs.

## Technologies Used

- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- OpenCV
- Seaborn
- scikit-learn
- KaggleHub

## Purpose

This project demonstrates how deep learning can be applied to OCR tasks by training a CNN model to recognize characters from image data. It is useful for understanding image preprocessing, computer vision classification, and character recognition workflows.
