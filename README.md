<h1 align="center">🧠 Face Intelligence Suite: COMSYS Hackathon-5, 2025</h1>


**"From Identity to Insight — Smarter Face Understanding using Deep Learning"**

Welcome to our official submission for the **COMSYS Hackathon-5 (2025)**! This repository contains a two-part intelligent facial analysis system built to tackle:

- **Task A**: Gender Classification from Facial Images
- **Task B**: Face Matching (Multi-Class Recognition with Distorted Inputs)

Each task is developed using cutting-edge deep learning techniques, blending **Convolutional Neural Networks (CNNs)**, **Vision Transformers (ViTs)**, **Metric Learning**, and **face embeddings** to ensure accuracy, explainability, and robustness.

---

## 📁 Repository Structure

```text
Face-Intelligence-COMSYS2025/
├── Task-A/
│   ├── images/               # Image assets for Task A
│   ├── Task-A.ipynb          # Jupyter Notebook for Task A
│   ├── requirements.txt      # Dependencies for Task A
│   └── README.md             # Documentation for Task A
├── Task-B/
│   ├── images/               # Image assets for Task B
│   ├── Task-B.ipynb          # Jupyter Notebook for Task B
│   ├── requirements.txt      # Dependencies for Task B
│   └── README.md             # Documentation for Task B
└── README.md                 # Main README for the overall project

```
---

## 🎯 Overview of Tasks

### ✅ Task A: Gender Classification (Male / Female)

A hybrid deep learning approach combining:
- **CNN (ResNet18)** for local feature extraction
- **Vision Transformer (ViT)** for global attention modeling

**Key Features**:
- Face detection via OpenCV Haar Cascades
- Data augmentation + normalization
- Real-time, visually explainable predictions
- Transfer learning from ImageNet for better generalization

**Performance**:
| Metric     | Training (%) | Validation (%) |
|------------|--------------|----------------|
| Accuracy   | 99.38        | 94.55          |
| Precision  | 99.80        | 94.01          |
| Recall     | 99.41        | 99.05          |
| F1 Score   | 99.61        | 96.47          |

🔍 **Architecture**: `CNN (ResNet18)` → `Feature Map` → `Vision Transformer Head`

📤 **Output**: Real-time gender classification with confidence scores and visual overlays.

---

### ✅ Task B: Face Verification with Distorted Inputs

A robust face matching pipeline using:
- **MTCNN** for precise face detection
- **InceptionResNetV1** (pretrained on VGGFace2) for face embeddings
- **Cosine Similarity** for similarity scoring
- Custom dataset handling distorted face images

**Key Features**:
- Embedding-based verification instead of fixed-class classification
- Threshold-based matching across unknown identities
- Evaluation through Accuracy, Precision, Recall, F1

**Performance**:
| Metric     | Training (%) | Validation (%) |
|------------|--------------|----------------|
| Accuracy   | 81.11        | 82.56          |
| Precision  | 92.09        | 92.57          |
| Recall     | 68.07        | 70.80          |
| F1 Score   | 78.28        | 80.24          |

🔍 **Architecture**: `MTCNN` → `Face Cropping` → `InceptionResNetV1` → `Cosine Distance` → `Match / No Match`

📤 **Output**: Verification label (1 or 0) with cosine distance score and visual evaluation.

---

## ⚙️ Installation

1. Clone the repository:

```bash
git clone https://github.com/suman2896/Face-Intelligence-COMSYS2025.git
cd Face-Intelligence-COMSYS2025
```

## 📦 Install Dependencies

### For Task A:
```bash
cd Task-A
pip install -r requirements.txt
```

### For Task B:
```bash
cd ../Task-B
pip install -r requirements.txt
```

---

## 🚀 Running the Code

### 🧠 Task A: Gender Classification

#### Train the Model:
```bash
python train.py \
  --data_dir data/ \
  --batch_size 32 \
  --lr 0.0001 \
  --epochs 15 \
  --output_dir models/
```

#### Make Predictions:
```bash
python predict.py \
  --image_path samples/test.jpg \
  --model_path models/best_model.pth
```

---

### 🧠 Task B: Face Verification

#### Run Verification:
```bash
python verify_faces.py \
  --train_dir /path/to/train \
  --val_dir /path/to/val \
  --batch_size 32 \
  --threshold 0.7
```

📤 Results will include cosine distances, confusion matrices, and visual verification plots.

---

## 📊 Evaluation & Visualizations

- Confusion matrices for classification and verification  
- Side-by-side comparison plots for predictions  
- Cosine distance heatmaps for face similarity scores  

---

## 🌍 Application Use Cases

| Domain             | Utility                                  |
|--------------------|-------------------------------------------|
| Surveillance       | Secure identity verification             |
| Access Control     | Gender/face-based entry systems          |
| Retail Analytics   | Demographic insights                     |
| Device Unlocking   | Face-based secure access                 |
| Attendance Systems | Automated employee/student verification  |

---

## 🔮 Future Scope

| Improvement Area     | Upgrade Plan                            |
|----------------------|------------------------------------------|
| Detection Accuracy   | Switch to RetinaFace / Dlib             |
| Backbone Model       | Explore ViT, EfficientNet               |
| Thresholding Strategy| ROC-based dynamic tuning                |
| Web App Interface    | Build using Streamlit or Flask          |
| Real-time Inference  | Optimize for edge devices & mobile      |

---

## 📌 Hackathon Compliance

✅ Model Diagrams (see `/images/`)  
✅ Clean, Commented Code  
✅ Reproducible Results  
✅ Evaluation Metrics Reported  
✅ Visual Output + Insights  
✅ Ready for Real-World Deployment  

---

## 🙌 Acknowledgements

- `facenet-pytorch` for embedding models  
- `VGGFace2 Dataset`  
- **COMSYS Hackathon 2025** for the challenge datasets and opportunity  

---

## ⭐ Like It?

If this project inspires you or helps your work, consider ⭐ starring the repo or connecting with the contributors.

---

## 📬 Contact

📧 chowdhurysuman1267@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/suman-chowdhury-655629312)  
🔗 [GitHub](https://github.com/suman2896)

📧 shreyakmukhrjeedgp@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/shreyak-mukherjee-203558275/)  
🔗 [GitHub](https://github.com/shreyakmukherjee)

📧 sayankumardhar2003@gmail.com 
🔗 [LinkedIn](https://www.linkedin.com/in/sayan-kumar-dhar-a5a405313)  
🔗 [GitHub](https://github.com/SayanDhar10)


