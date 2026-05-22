# 🧠 Brain Tumor Detection from MRI Images
### *AI-Powered Medical Image Analysis using Image Processing & Machine Learning*

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge&logo=python">
  <img src="https://img.shields.io/badge/OpenCV-Computer%20Vision-green?style=for-the-badge&logo=opencv">
  <img src="https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange?style=for-the-badge&logo=scikitlearn">
  <img src="https://img.shields.io/badge/Google%20Colab-Notebook-yellow?style=for-the-badge&logo=googlecolab">
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge">
</p>

---

<p align="center">
  <img src="images/banner.png" width="100%">
</p>

---

# 📌 Overview

This project presents a complete **Brain Tumor Detection System** developed using traditional **Image Processing** and **Machine Learning** techniques.

The system automatically analyzes MRI brain scan images and classifies them into:

✅ Tumor MRI  
✅ Normal MRI

The project combines:

- 🖼️ Digital Image Processing
- 🧠 Medical Image Analysis
- 🤖 Machine Learning
- 👁️ Computer Vision

to create an automated MRI classification pipeline.

---

# ✨ Features

<div align="center">

| Feature | Description |
|---|---|
| 🖼️ MRI Preprocessing | Enhances MRI quality |
| 🌫️ Gaussian Blur | Removes image noise |
| 📈 Histogram Equalization | Improves contrast |
| 🧩 Tumor Segmentation | Detects suspicious regions |
| ✂️ Edge Detection | Structural boundary extraction |
| 🔍 Contour Detection | Tumor region localization |
| 📦 Feature Extraction | MRI image statistics |
| 🌲 Random Forest Model | MRI classification |
| 📊 Confusion Matrix | Performance evaluation |
| 🤖 Automated Pipeline | End-to-end processing |

</div>

---

# 🧠 Technologies Used

<p align="center">

<img src="https://skillicons.dev/icons?i=python,opencv,sklearn" />

</p>

| Technology | Purpose |
|---|---|
| Python | Core Programming |
| OpenCV | Image Processing |
| NumPy | Numerical Computing |
| Matplotlib | Visualization |
| Scikit-learn | Machine Learning |
| Google Colab | Development Environment |

---

# 📂 Project Structure

```bash
Brain-Tumor-Detection/
│
├── imageproc_032.ipynb
├── Report-032.pdf
├── README.md
├── dataset.zip
│
├── images/
│   ├── banner.png
│   ├── sample_results.png
│   ├── segmentation.png
│   └── confusion_matrix.png
│
├── output/
│   ├── preprocessing_results/
│   ├── segmentation_results/
│   ├── confusion_matrix/
│   └── predictions/
│
└── requirements.txt
```

---

# 🧪 MRI Processing Pipeline

<p align="center">
  <img src="images/pipeline.png" width="85%">
</p>

```text
MRI Image
   ↓
Grayscale Conversion
   ↓
Gaussian Blur
   ↓
Histogram Equalization
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
```

---

# 📊 Dataset Information

The dataset contains MRI brain scans divided into:

- 🧠 Tumor Images
- ✅ Normal Images

All MRI images were resized to:

```python
224 × 224 pixels
```

before processing.

---

# ⚙️ Image Preprocessing

## 🔹 Grayscale Conversion

```python
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
```

---

## 🔹 Gaussian Blur

```python
blurred = cv2.GaussianBlur(gray, (5,5), 0)
```

---

## 🔹 Histogram Equalization

```python
equalized = cv2.equalizeHist(blurred)
```

---

# 🧩 Tumor Segmentation

## 🔹 Thresholding

```python
_, thresh = cv2.threshold(equalized, 45, 255, cv2.THRESH_BINARY)
```

---

## 🔹 Edge Detection

```python
edges = cv2.Canny(equalized, 50, 150)
```

---

## 🔹 Morphological Operations

```python
kernel = np.ones((3,3), np.uint8)

opened = cv2.morphologyEx(
    thresh,
    cv2.MORPH_OPEN,
    kernel
)
```

---

## 🔹 Contour Detection

```python
contours, _ = cv2.findContours(
    opened,
    cv2.RETR_EXTERNAL,
    cv2.CHAIN_APPROX_SIMPLE
)
```

Bounding boxes are drawn around suspicious tumor regions.

---

# 🧠 Feature Extraction

The following image features are extracted:

| Feature | Description |
|---|---|
| Mean Intensity | Average pixel value |
| Standard Deviation | Pixel variation |
| Edge Pixel Count | Number of edge pixels |
| Contour Count | Number of contours |
| Largest Contour Area | Tumor region size |
| Texture Features | MRI texture information |

---

# 🤖 Machine Learning Model

The project uses a **Random Forest Classifier** for MRI classification.

```python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier(
    n_estimators=100,
    random_state=42
)

model.fit(X_train, y_train)
```

---

# 📈 Model Evaluation

The trained model is evaluated using:

✅ Accuracy Score  
✅ Confusion Matrix  
✅ Classification Report

```python
from sklearn.metrics import (
    accuracy_score,
    classification_report,
    confusion_matrix
)
```

---

# 📷 Output Results

## 🧠 MRI Segmentation

<p align="center">
  <img src="images/segmentation.png" width="70%">
</p>

---

## 📊 Confusion Matrix

<p align="center">
  <img src="images/confusion_matrix.png" width="55%">
</p>

---

## 🔍 Sample Predictions

<p align="center">
  <img src="images/sample_results.png" width="80%">
</p>

---

# 🖥️ Required Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
import os
import random

from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier

from sklearn.metrics import (
    accuracy_score,
    classification_report,
    confusion_matrix
)
```

---

# 📚 Learning Outcomes

This project demonstrates practical implementation of:

✅ Digital Image Processing  
✅ MRI Image Analysis  
✅ Medical Imaging  
✅ Computer Vision  
✅ Feature Engineering  
✅ Machine Learning Classification  
✅ OpenCV Operations  
✅ Random Forest Algorithms  

---

# ⚠️ Limitations

- MRI image quality affects performance
- Small datasets may reduce generalization
- False positives can occur during contour detection
- Traditional ML models are less powerful than Deep Learning approaches

---

# 🔮 Future Improvements

✅ CNN-Based Deep Learning Models  
✅ U-Net Tumor Segmentation  
✅ Streamlit / Flask Web Application  
✅ Real-Time MRI Analysis  
✅ Multi-Class Tumor Classification  
✅ Cloud Deployment  
✅ Larger Medical Datasets  

---

# 📌 Conclusion

This project successfully demonstrates how **Image Processing** and **Machine Learning** techniques can be combined for automated brain tumor detection from MRI images.

The system performs:

✔ MRI preprocessing  
✔ Tumor segmentation  
✔ Contour analysis  
✔ Feature extraction  
✔ Random Forest classification  

to classify MRI scans as:

🧠 Tumor  
✅ Normal

The project provides a strong foundation for advanced AI-based medical imaging applications and healthcare automation systems.

---

# 📜 License

This project is developed for educational and academic purposes only.

 

---

<p align="center">
  <b>🧠 AI for Healthcare • Medical Imaging • Computer Vision</b>
</p>
