# 🧠 Face Verification with MTCNN + InceptionResNetV1 (VGGFace2)

> "Smarter Identity Verification Using Deep Metric Learning and Real Face Cropping."

---

## 🔍 Overview

This project implements a face verification system using a deep learning pipeline with:

* **MTCNN** for robust face detection
* **InceptionResNetV1** (pretrained on VGGFace2) for feature extraction
* **Cosine Similarity** for comparing embeddings

It evaluates similarity between pairs of faces using a custom PyTorch `Dataset` built on face image folders with distortions.

---

## 🎯 Objective

To determine whether two face images belong to the same identity using face embedding comparison.

---

## 📷 Pipeline Summary

1. **Face Detection:**

   * Crops and aligns faces using MTCNN

2. **Embedding Generation:**

   * Uses pretrained InceptionResNetV1 (VGGFace2)

3. **Verification:**

   * Measures cosine similarity between embeddings
   * Threshold-based classification: Match or No Match

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





## 🧠 Model Architecture

<div align="center">
<img src="https://github.com/suman2896/Face-Intelligence-COMSYS2025/blob/main/Task-B/images/Model_Architecture_task2.png" width="500"/>
</div>

* **MTCNN**: Detects and aligns faces
* **InceptionResNetV1**: Outputs 512D embeddings for each face
* **Cosine Similarity**: Compares embeddings for verification

---


## 🧪 Training & Evaluation

No training needed for the embedder (pretrained). Instead, pairs are evaluated and scored.

### Metrics Used:

<div align="center">

| Metric    | Description                        |
| --------- | ---------------------------------- |
| Accuracy  | Overall classification correctness |
| Precision | True positive rate for Match       |
| Recall    | Detection rate for actual matches  |
| F1 Score  | Balanced precision and recall      |

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

<!-- Training Section -->
<div align="center">
  <h3 style="font-weight: bold; font-size: 18px; margin-bottom: 10px;">🧠 Training Results</h3>
  <img src="https://github.com/suman2896/Face-Intelligence-COMSYS2025/blob/3a82b1fced6f22242b4a7a4a9c98f9bcab1fa7d2/Task-B/images/Training_Confusion_Matrix.png" height="300"/>
  <img src="https://github.com/suman2896/Face-Intelligence-COMSYS2025/blob/3a82b1fced6f22242b4a7a4a9c98f9bcab1fa7d2/Task-B/images/Training_Face_Verification.png" height="300"/>
</div>

<br>

<!-- Validation Section -->
<div align="center">
  <h3 style="font-weight: bold; font-size: 18px; margin-bottom: 10px;">🔍 Validation Results</h3>
  <img src="https://github.com/suman2896/Face-Intelligence-COMSYS2025/blob/3a82b1fced6f22242b4a7a4a9c98f9bcab1fa7d2/Task-B/images/Validation_Confusion_Matrix.png" height="300"/>
  <img src="https://github.com/suman2896/Face-Intelligence-COMSYS2025/blob/3a82b1fced6f22242b4a7a4a9c98f9bcab1fa7d2/Task-B/images/Validation_Face_Verification.png" height="300"/>
</div>



---


## 🖼️ Output Visualization

<div align="center">
  
  <img src="https://github.com/suman2896/Face-Intelligence-COMSYS2025/blob/main/Task-B/images/Final_Output.png" height="320"/>

</div>

</div>

---


## 🧠 Why This Works

* 🔍 Real face cropping > random resizing
* 🧠 Pretrained embedding extractor with deep metric learning
* 🔎 Cosine-based matching for robustness

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

## 🚀 Getting Started

### 1. 📦 Installation
```bash
pip install -r requirements.txt
```

### 2. 🧪 Run Face Verification
```bash
python verify_faces.py \
  --train_dir /path/to/train \
  --val_dir /path/to/val \
  --batch_size 32 \
  --threshold 0.7
```

### 3. 📊 Visualize Results
Confusion matrices, cosine distance plots, and sample verification pairs will be displayed automatically after evaluation.

### 4. 📤 Expected Output
```text
✅ Face detected using MTCNN!
🧠 Embeddings generated via InceptionResNetV1
🔍 Distance: 0.4321 → Prediction: Match
📊 Metrics and visualizations saved in /outputs/
```

---

## ⭐ If You Like It...

Star ⭐ the repo, fork it, or share with your peers.  
Your support drives open research and reproducibility!

```bash
git clone https://github.com/your-username/mtcnn-face-verification.git
```

---

## 🌟 Final Note: Hackathon Ready, Industry Ready

This isn’t just a demo—it’s a deployable, robust, and modular face verification engine:

- 🔍 **Accurate**: Verified performance with real-world distortions  
- 🧠 **Intelligent**: Face-centric preprocessing + VGGFace2 deep embeddings  
- 📦 **Plug & Play**: Just point to folders and evaluate—no model training required  
- 🚀 **Deployment-Ready**: Lightweight and easy to integrate with web or edge systems

> 💡 Built with clarity, speed, and trust in AI.


---

## 📬 Credits

* [facenet-pytorch](https://github.com/timesler/facenet-pytorch)
* [VGGFace2 Dataset](https://www.robots.ox.ac.uk/~vgg/data/vgg_face2/)
* Hackathon Dataset: COMSYS 2025 Challenge

---

> 🔐 Built with performance, explainability, and fairness in mind.
