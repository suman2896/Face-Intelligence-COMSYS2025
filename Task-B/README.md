<div align="center">
<h1> 🧠 Gender Classification with CNN-ViT Fusion  </h1> 
</div>

> "Merging Face Detection with Deep Visual Reasoning for Smarter Gender Recognition."

<div align="center">
<h3> Developed as part of the Hackathon 2025 Series </h3>
</div>

---

## 🎯 Objective

This project aims to classify **gender (Male/Female)** from facial images using a hybrid approach that integrates **CNN** (for local feature extraction) and **Vision Transformers (ViT)** (for global attention).  
Built with **Facenet-PyTorch + Custom ViT Head**, the model achieves explainable and efficient inference suitable for real-world use.

---

## 🧠 System Architecture

<div align="center">
<!-- Insert system architecture diagram here -->
<img src="images/system_architecture.png" width="700"/>
</div>

---

## 🔧 Methodology Overview

### A. 🖼️ Data Preprocessing

<div align="center">

| Step              | Description                                                  |
|-------------------|--------------------------------------------------------------|
| **Face Detection** | `MTCNN` is used for precise and robust face extraction.     |
| **Transforms**     | Resize → Tensor → Normalize (ImageNet Mean/Std).            |
| **Augmentation**   | Random horizontal flip to generalize across face poses.     |

</div>

---

### B. 🏗️ Model Pipeline

<div align="center">

| Component             | Description                                                              |
|-----------------------|--------------------------------------------------------------------------|
| **Feature Extractor** | `InceptionResnetV1` from facenet-pytorch (pretrained on VGGFace2).       |
| **ViT Head**          | Custom transformer layers to learn global context from facial embeddings.|
| **Classifier**        | Fully Connected (FC) layers → Gender prediction.                         |

</div>

---

### 🧪 Training Configuration

<div align="center">

| Hyperparameter    | Value            |
|------------------|------------------|
| **Loss Function** | CrossEntropyLoss |
| **Optimizer**     | Adam             |
| **Learning Rate** | 1e-4             |
| **Batch Size**    | 32               |
| **Epochs**        | 15               |

</div>

---

## 📊 Evaluation Metrics

<div align="center">

| Metric     | Train (%) | Validation (%) |
|------------|-----------|----------------|
| Accuracy   | 81.11     | 82.56          |
| Precision  | 92.09     | 92.57          |
| Recall     | 68.07     | 70.80          |
| F1-Score   | 78.28     | 80.24          |

</div>

---

## 🖼️ Output Visualization

<div align="center">

| Original Image | Predicted Output |
|----------------|------------------|
| <img src="images/Original_image.png" width="250"/> | <img src="images/Output_image.png" width="250"/> |

</div>

---

## 🌍 Application Use Cases

<div align="center">

| Domain            | Utility                                                   |
|------------------|-----------------------------------------------------------|
| Surveillance      | Gender-based access control, security cameras            |
| Retail            | Customer analytics for demographic insight               |
| Social Robotics   | Gender-aware interaction in real-time                    |
| Mobile Edge AI    | Lightweight ViT enables on-device real-time inference    |

</div>

---

## 🔮 Future Scope

<div align="center">

| Feature             | Upgrade Plan                         |
|---------------------|--------------------------------------|
| Face Detection      | Replace MTCNN with RetinaFace        |
| Backbone Upgrade    | Try EfficientNet + DeiT              |
| Web Interface       | Deploy using Streamlit               |
| Federated Training  | Enable privacy-preserving learning   |

</div>

---

## 🚀 How to Run

### 1. 🧩 Install Dependencies
```bash
pip install -r requirements.txt

