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
├── Raw_dataset/
│   ├── ISBI2016_ISIC_Part1_Training_Data/
|   ├── ISBI2016_ISIC_Part1_Training_GroundTruth/
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
| Basic U-Net                 | ~0.75            | ~0.62            |
| U-Net + Augmentation + Loss | ~0.8559          | ~0.7554          |
| Attention U-Net + Grad-CAM  | ~0.8636          | ~0.7643          |

---

## 🔍 Grad-CAM Visualization

Grad-CAM is used to highlight important regions in the input image that influence the model’s prediction. This improves interpretability, especially in medical applications.

---

## ⚙️ Setup & Usage

### ▶️ Running on Google Colab (Recommended)

1. Download the dataset ZIP files (not included in this repository due to size constraints ~600MB+).

2. Open the notebook in Google Colab.

3. Upload or mount the ZIP files (e.g., via Google Drive).

4. Update the following variables in the preprocessing cell:

   ```python
   zip_path = "path_to_images_zip"
   zip_path2 = "path_to_masks_zip"
   ```

5. Run all cells sequentially.

---

### 💻 Running Locally

#### 📁 Step 1: Set Working Directory

Ensure your current working directory is:

```
project_root/notebooks/
```

---

#### 📦 Step 2: Install Dependencies

```
pip install -r requirements.txt
```

---

#### ▶️ Step 3: Run Notebook

* Skip the **first 3 cells** (used for Colab setup)
* Start execution from the dataset preprocessing cell

---

#### 🔧 Step 4: Update Dataset Paths

In the preprocessing cell, switch from Colab paths to local paths:

👉 Uncomment these:

```python
RAW_IMG_DIR = "../Raw_Dataset/ISBI2016_ISIC_Part1_Training_Data"
RAW_MASK_DIR = "../Raw_Dataset/ISBI2016_ISIC_Part1_Training_GroundTruth"

NEW_IMG_DIR = "../dataset/images"
NEW_MASK_DIR = "../dataset/masks"
```

👉 Comment out these:

```python
RAW_IMG_DIR = "/content/unzip/ISBI2016_ISIC_Part1_Training_Data"
RAW_MASK_DIR = "/content/unzip/ISBI2016_ISIC_Part1_Training_GroundTruth"

NEW_IMG_DIR = "/content/dataset/images"
NEW_MASK_DIR = "/content/dataset/masks"
```

---

#### ▶️ Step 5: Run Remaining Cells

* Execute the preprocessing cell to organize dataset
* Then run the rest of the notebook normally

---

## 📌 Notes

* The notebooks are configured for Google Colab by default.
* Local execution requires manual path adjustment as described above.
* Ensure the dataset folder structure is consistent before training.


---

## 📁 Dataset

* ISIC Skin Lesion Dataset
* Images and corresponding segmentation masks

---

## 📈 Evaluation Metrics

* Dice Coefficient
* Intersection over Union (IoU)

---

## 📌 Conclusion

This project demonstrates how progressive improvements in architecture and training strategies can significantly enhance segmentation performance, while also improving model interpretability.
