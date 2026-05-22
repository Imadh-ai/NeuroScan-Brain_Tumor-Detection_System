🧠 Brain Tumor Detection from MRI Images

A complete Image Processing and Machine Learning project for detecting brain tumors from MRI scans using Python, OpenCV, and Scikit-learn.

⸻

📌 Project Overview

This project implements an automated Brain Tumor Detection System using traditional image processing and machine learning techniques.

The system processes MRI brain scan images, performs preprocessing and segmentation, extracts meaningful image features, and classifies MRI scans into:

* Tumor MRI
* Normal MRI

The project was developed using:

* Python
* OpenCV
* NumPy
* Matplotlib
* Scikit-learn
* Google Colab

The objective of the project is to assist medical image analysis by reducing manual effort and improving tumor identification efficiency.

⸻

🚀 Features

✅ MRI image preprocessing

✅ Histogram Equalization

✅ Gaussian Blur noise reduction

✅ Tumor segmentation using thresholding

✅ Canny edge detection

✅ Morphological operations

✅ Contour detection and bounding boxes

✅ Feature extraction from MRI images

✅ Random Forest Classification

✅ Confusion Matrix visualization

✅ Classification Report generation

✅ End-to-end automated pipeline

⸻

🧠 Technologies Used

Technology	Purpose
Python	Core Programming
OpenCV	Image Processing
NumPy	Numerical Operations
Matplotlib	Visualization
Scikit-learn	Machine Learning
Google Colab	Development Environment

⸻

📂 Project Structure

Brain-Tumor-Detection/
│
├── imageproc_032.ipynb          # Main Google Colab notebook
├── Report-032.pdf               # Project report
├── README.md                    # GitHub documentation
├── dataset.zip                  # MRI dataset
│
├── output/
│   ├── preprocessing_results/
│   ├── segmentation_results/
│   ├── confusion_matrix/
│   └── predictions/
│
└── images/
    ├── sample_results.png
    ├── segmentation.png
    └── confusion_matrix.png

⸻

📊 Dataset Information

The dataset contains MRI brain scan images divided into two categories:

* Tumor Images
* Normal Images

All MRI scans were resized to:

224 × 224 pixels

before being processed by the pipeline.

⸻

⚙️ Project Workflow

1️⃣ Dataset Upload

The dataset ZIP file is uploaded into Google Colab.

uploaded = files.upload()

⸻

2️⃣ Image Preprocessing

Several preprocessing techniques are applied to improve MRI image quality.

✔ Grayscale Conversion

Converts RGB images into grayscale.

gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

✔ Gaussian Blur

Removes image noise and smooths the MRI scan.

blurred = cv2.GaussianBlur(gray, (5,5), 0)

✔ Histogram Equalization

Improves image contrast.

equalized = cv2.equalizeHist(blurred)

⸻

🧪 Preprocessing Pipeline

MRI Image
   ↓
Grayscale Conversion
   ↓
Gaussian Blur
   ↓
Histogram Equalization
   ↓
Enhanced MRI Image

⸻

🧩 Tumor Segmentation

The project identifies suspicious tumor regions using multiple image processing methods.

✔ Thresholding

Separates foreground from background.

_, thresh = cv2.threshold(equalized, 45, 255, cv2.THRESH_BINARY)

✔ Canny Edge Detection

Detects structural boundaries.

edges = cv2.Canny(equalized, 50, 150)

✔ Morphological Operations

Removes small noise artifacts.

kernel = np.ones((3,3), np.uint8)
opened = cv2.morphologyEx(thresh, cv2.MORPH_OPEN, kernel)

✔ Contour Detection

Detects candidate tumor regions.

contours, _ = cv2.findContours(opened, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)

Bounding boxes are drawn around detected regions.

⸻

🧠 Feature Extraction

The following features are extracted from MRI images:

Feature	Description
Mean Intensity	Average pixel value
Standard Deviation	Intensity variation
Edge Pixel Count	Number of edge pixels
Contour Count	Number of contours
Largest Contour Area	Size of detected region
Texture Features	MRI texture characteristics

⸻

🤖 Machine Learning Model

A Random Forest Classifier is trained using extracted image features.

from sklearn.ensemble import RandomForestClassifier
model = RandomForestClassifier(n_estimators=100)
model.fit(X_train, y_train)

⸻

📈 Model Evaluation

The model performance is evaluated using:

* Accuracy Score
* Confusion Matrix
* Classification Report

from sklearn.metrics import confusion_matrix, classification_report

⸻

📷 Output Results

The project generates:

* Original MRI Images
* Preprocessed MRI Images
* Edge Detection Outputs
* Tumor Segmentation Results
* Contour Detection Results
* Confusion Matrix
* Final Predictions

⸻

📌 Sample Pipeline

MRI Image
   ↓
Preprocessing
   ↓
Thresholding
   ↓
Edge Detection
   ↓
Morphological Operations
   ↓
Contour Detection
   ↓
Feature Extraction
   ↓
Random Forest Classification
   ↓
Tumor / Normal Prediction

⸻

▶️ How to Run the Project

Step 1 — Clone Repository

git clone https://github.com/your-username/Brain-Tumor-Detection.git

⸻

Step 2 — Install Dependencies

pip install opencv-python numpy matplotlib scikit-learn

⸻

Step 3 — Open Notebook

Open the notebook in:

* Google Colab
* Jupyter Notebook

⸻

Step 4 — Upload Dataset ZIP

Upload the MRI dataset ZIP file when prompted.

⸻

Step 5 — Run All Cells

Execute all notebook cells sequentially.

⸻

🖥️ Required Libraries

import cv2
import numpy as np
import matplotlib.pyplot as plt
import os
import random
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score
from sklearn.metrics import classification_report
from sklearn.metrics import confusion_matrix

⸻

📚 Key Learning Outcomes

This project demonstrates practical implementation of:

* Digital Image Processing
* Medical Image Analysis
* Computer Vision
* MRI Segmentation
* Feature Engineering
* Machine Learning Classification
* OpenCV Operations
* Random Forest Algorithms

⸻

⚠️ Limitations

* Performance depends on MRI image quality
* Small datasets may reduce generalization
* False positives can occur during contour detection
* Traditional ML methods are less powerful than deep learning models

⸻

🔮 Future Improvements

Future versions of this project can include:

✅ Deep Learning CNN Models

✅ U-Net Segmentation

✅ Real-time MRI Analysis

✅ Web Application Deployment

✅ Flask / Streamlit Interface

✅ Larger Medical Datasets

✅ Multi-class Tumor Classification

⸻

📌 Conclusion

This project successfully demonstrates how image processing and machine learning techniques can be combined to detect brain tumors from MRI images.

The system applies preprocessing, segmentation, contour analysis, feature extraction, and Random Forest classification to automatically identify tumor and normal MRI scans.

The project provides a strong foundation for advanced medical imaging and AI-based healthcare applications.

⸻

👨‍💻 Author

IMAAD AHAMED

Artificial Intelligence & Machine Learning Undergraduate

Specializations:

* AI & Machine Learning
* Computer Vision
* Image Processing
* Deep Learning
* IoT & Robotics


⸻

📜 License

This project is for educational and academic purposes.

⸻

🌟 If you like this project

Give this repository a ⭐ on GitHub.
