# 🩺 Skin Lesion Segmentation using U-Net (ISIC 2018)

This repository implements a **deep learning-based medical image segmentation pipeline** using the **U-Net** architecture to segment skin lesions in the **ISIC 2018 dataset**.  
It demonstrates the feasibility of building an accurate baseline for biomedical segmentation tasks using **PyTorch**, **Albumentations**, and **Google Colab** under computational constraints.

---

## 📚 Project Overview
Accurate skin lesion segmentation is crucial for automated dermatological analysis, impacting performance in tasks such as feature extraction, classification, and disease diagnosis. Skin cancer, especially melanoma, is one of the most common and deadly cancers worldwide. Early detection via dermoscopic imaging enhances survival rates, highlighting the need for reliable computer-aided segmentation systems.  
This project implements a **U-Net** model trained on the **ISIC 2018 Challenge dataset** to segment dermoscopic images of skin lesions.

---

## 🧠 Model Architecture
The implemented U-Net consists of:
- **Encoder–decoder structure** with skip connections.
- **Four down-sampling blocks**, a bottleneck, and four up-sampling blocks.
- **Dice loss** for imbalance mitigation.
- **Adam optimizer** with learning rate `1e-4`.

## 🧠 Key Results
| Metric | Validation Score |
|---------|------------------|
| IoU     | 0.628 |
| Dice    | 0.758 |
| Accuracy| 0.893 |

---

## ⚙️ Implementation Details

| Component | Description |
|------------|-------------|
| **Framework** | PyTorch |
| **Data Augmentation** | Albumentations (resize, flip, brightness/contrast) |
| **Loss Function** | Dice Loss |
| **Metrics** | IoU, Dice Coefficient, Pixel Accuracy |
| **Optimizer** | Adam (LR = 1e-4) |
| **Hardware** | Google Colab (Tesla T4 GPU, 16GB VRAM) |

---

## 📦 Dataset
- **Source**: [ISIC 2018: Skin Lesion Analysis Challenge](https://challenge2018.isic-archive.com/)
- **Training images**: 2,594  
- **Test images**: 1,000  
- **Annotations**: Binary lesion masks at the pixel level.  
- Images accessed **directly from ZIP archives** for memory efficiency.

---

## 📊 **Results & Discussion**

- **Best model checkpoint**: /content/drive/MyDrive/best_unet.pt
- **Validation IoU**: 0.628
- **Dice Coefficient**: 0.758
- **Accuracy**: 0.893

Performance shows stable convergence and good lesion boundary capture despite the limited dataset subset.
--

## 🚀 Running the Project

🧩 1. requirements:

torch>=2.0.0
torchvision>=0.15.0
torchaudio
albumentations>=1.3.0
segmentation-models-pytorch>=0.3.3
opencv-python
matplotlib
tqdm
pillow
numpy


2️⃣ Install Dependencies
Download the following ZIP files from ISIC 2018 and place them in your working directory:
        - ISIC2018_Task1-2_Training_Input.zip
        - ISIC2018_Task1-2_Test_Input.zip
        - ISIC2018_Task1_Training_GroundTruth.zip
Update their paths in:
        - BASE_DIR = '/content/drive/MyDrive/'

RUN THE SCRIPT: 
        - python lesion_image_segementation.py

🧩 Future Work
        -Use pretrained encoders (ResNet, EfficientNet)
        -Implement GAN-based data augmentation
        -Explore semi-supervised or transformer-based U-Nets (TransUNet)
        -Integrate explainability (e.g., Grad-CAM)

📜 Citation

If you use this repository, please cite:
        - Guzmán, H. (2025). Skin Lesion Segmentation using U-Net: A Baseline Study on ISIC 2018.
