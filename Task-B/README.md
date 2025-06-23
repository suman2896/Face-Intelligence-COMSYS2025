<div align="center">
<h1> 🧠 Gender Classification with CNN-ViT Fusion  </h1> 
</div>

> "Merging Face Detection with Deep Visual Reasoning for Smarter Gender Recognition."

<div align="center">
<h3> Developed as part of the Hackathon 2025 Series </h3>
</div>

---

## 🎯 Objective

This project aims to perform **face verification** by determining whether two facial images belong to the same individual.  
Using **Facenet-PyTorch’s InceptionResnetV1** for feature extraction and **cosine similarity** for verification, the system provides an efficient and scalable solution for identity matching in real-world scenarios.

---

## 🧠 System Architecture

<div align="center">
<!-- Insert system architecture diagram here -->
<img src="images/system_architecture.png" width="700"/>
</div>

---

## 🔧 Methodology Overview

### 🖼️ Data Preprocessing

<div align="center">

| Step               | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| **Face Detection** | Used `MTCNN` to detect and extract faces with added margin around the face. |
| **Face Cropping**  | Automatically crops the detected face from the image using bounding boxes.  |
| **Transforms**     | Resize to 160×160 → Tensor conversion → Normalize with mean=[0.5, 0.5, 0.5] and std=[0.5, 0.5, 0.5]. |


</div>


---

### 🏗️ Model Pipeline

<div align="center">

| Component             | Description                                                                 |
|-----------------------|-----------------------------------------------------------------------------|
| **Feature Extractor** | `InceptionResnetV1` from facenet-pytorch (pretrained on VGGFace2) to extract facial embeddings. |
| **Similarity Metric** | Cosine similarity is used to measure the distance between facial embeddings. |
| **Decision Rule**     | A threshold-based classifier determines if the input faces belong to the same person (face match) or not. |

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
|-------------------|-----------------------------------------------------------|
| Surveillance      | Face verification for secure access and identity monitoring. |
| Attendance Systems| Automated attendance tracking using face verification.    |
| Device Unlocking  | Face-based authentication for personal devices.           |
| E-commerce        | Secure customer verification for high-value transactions. |

</div>


---

## 🔮 Future Scope

<div align="center">

| Feature             | Upgrade Plan                                |
|---------------------|---------------------------------------------|
| Face Detection      | Upgrade from MTCNN to RetinaFace for more accurate and faster detection. |
| Backbone Upgrade    | Explore more modern architectures like EfficientNet or ViT for better feature extraction. |
| Performance Tuning  | Optimize threshold selection dynamically based on ROC curve analysis. |
| Web Interface       | Develop a real-time face verification app using Streamlit or Flask. |
| Dataset Expansion   | Incorporate more diverse datasets to improve model generalization. |

</div>


---

## 🚀 How to Run

### 1. 🧩 Install Dependencies
```bash
pip install -r requirements.txt

