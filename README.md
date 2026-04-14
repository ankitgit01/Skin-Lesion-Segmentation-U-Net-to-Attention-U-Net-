# ISIC Skin Lesion Segmentation with U-Net Variants

## 📌 Overview

This project focuses on skin lesion segmentation using deep learning techniques on the ISIC dataset. Starting from a baseline U-Net model, multiple improvements are implemented to enhance performance and interpretability.

The project demonstrates how architectural modifications and training strategies impact segmentation quality in medical imaging tasks.

---

## 🚀 Features

* Baseline U-Net implementation
* Data augmentation using Albumentations
* Hybrid loss function (BCE + Dice Loss)
* Attention U-Net implementation
* Grad-CAM visualization for model interpretability
* Performance evaluation using Dice Score and IoU

---

## 📂 Repository Structure

```
├── notebooks/
│   ├── 1_basic_unet.ipynb
│   ├── 2_unet_augmented_loss.ipynb
│   ├── 3_attention_unet_gradcam.ipynb
├── dataset/
│   ├── images/
│   ├── masks/
├── outputs/
│   ├── predictions/
│   ├── visualizations/
├── zip/
│   ├── uncleaned_dataset/
│   ├── ISBI2016_ISIC_Part1_Training.zip
|   ├── ISBI2016_ISIC_Part1_Training_GroundTruth.zip
└── README.md
```

---

## 🧠 Methodology

### 1. Baseline Model

* U-Net architecture for binary segmentation
* BCEWithLogitsLoss
* Standard preprocessing

### 2. Improved Model

* Data augmentation (flip, rotation, brightness)
* Combined loss: BCE + Dice Loss
* Improved generalization

### 3. Advanced Model

* Attention U-Net for better feature focus
* Grad-CAM for visual explanation of predictions

---

## 📊 Results

| Model Version               | Dice Score       | IoU Score        |
| --------------------------- | ---------------- | ---------------- |
| Basic U-Net                 | ~0.75            | ~0.65            |
| U-Net + Augmentation + Loss | ~0.80            | ~0.70            |
| Attention U-Net + Grad-CAM  | ~0.82 (expected) | ~0.72 (expected) |

---

## 🔍 Grad-CAM Visualization

Grad-CAM is used to highlight important regions in the input image that influence the model’s prediction. This improves interpretability, especially in medical applications.

---

## ⚙️ Setup & Usage

### ▶️ Running on Google Colab (Recommended)

* Open the notebooks directly in Google Colab
* Upload or mount dataset
* Run all cells

### 💻 Running Locally

* Install required libraries:

  ```
  pip install torch torchvision albumentations opencv-python matplotlib
  ```
* Update dataset paths in the notebook before running

---

## 📁 Dataset

* ISIC Skin Lesion Dataset
* Images and corresponding segmentation masks

---

## 📈 Evaluation Metrics

* Dice Coefficient
* Intersection over Union (IoU)

---

## 🎯 Key Contributions

* Implementation of multiple U-Net variants
* Integration of hybrid loss for improved segmentation
* Use of Grad-CAM for explainability
* Comparative analysis of model performance

---

## 📌 Conclusion

This project demonstrates how progressive improvements in architecture and training strategies can significantly enhance segmentation performance, while also improving model interpretability.

---

## 📎 Note

The notebooks are designed to run on Google Colab by default. If running locally, make sure to update dataset paths accordingly.
