# 🌾 Automated Rice Grain Quality Analysis and Grade Classification using Deep Learning

---

# 📖 Overview

This project presents an automated deep learning framework for **Rice Grain Detection, Classification, and Quality Grading** using Computer Vision techniques. Traditional rice quality assessment relies on manual inspection, which is time-consuming, labor-intensive, and prone to human error. The proposed system combines **YOLOv8 object detection** and **custom Convolutional Neural Networks (CNNs)** to automatically detect individual rice grains, classify rice varieties and defects, and assign an overall quality grade based on the percentage of defective grains.

The trained models are integrated into a **Streamlit web application**, enabling real-time rice quality assessment from bulk rice images.

---

# 🎯 Objectives

- Develop an automated rice grain quality assessment system.
- Detect multiple rice grains from bulk rice images using YOLOv8.
- Classify rice varieties using a custom CNN model.
- Identify defective rice grains such as Broken, Chalky, Healthy, and Discolored grains.
- Automatically calculate defect percentage and assign quality grades.
- Deploy the complete system through a real-time Streamlit web application.

---

# ✨ Features

- 🌾 Rice Variety Classification (5 Classes)
- 🔍 Rice Grain Detection using YOLOv8
- ⚠️ Rice Defect Classification (4 Classes)
- 🏆 Automated Rice Grade Classification
- 🧠 Custom 10-Layer CNN Models
- ⚡ Real-Time Streamlit Deployment
- 📊 Automatic Grain Counting
- 📈 Confusion Matrix & Performance Evaluation

---

# 📊 Performance

## Rice Variety Classification

| Metric | Value |
|---------|-------|
| Training Accuracy | **96%** |
| Validation Accuracy | **95%** |

---

## Rice Defect Classification

| Metric | Value |
|---------|-------|
| Training Accuracy | **96%** |
| Validation Accuracy | **95%** |

---

## YOLOv8 Rice Grain Detection

| Metric | Value |
|---------|-------|
| mAP@50 | **0.94** |

---

# 📂 Datasets

This project utilizes multiple publicly available rice grain datasets along with real-time captured images.

---

## 1️⃣ Rice Variety Dataset

**🔗 Dataset:**  
`<Rice Variety Dataset Link>`

### Description

This dataset contains approximately **75,000 single rice grain images** belonging to five rice varieties:

- Arborio
- Basmati
- Ipsala
- Jasmine
- Karacadag

Each variety contains approximately **15,000 images** captured under controlled conditions.

The dataset was used to train the **Rice Variety Classification CNN**.

---

## 2️⃣ Rice Defect Dataset

**🔗 Dataset:**  
`<Rice Defect Dataset Link>`

### Description

This dataset consists of single-grain rice images categorized into:

- Broken Rice
- Chalky Rice
- Healthy Rice
- Discolored Rice

The dataset was used to train the **Rice Defect Classification CNN**.

---

## 3️⃣ Rice Grading Dataset

**🔗 Dataset:**  
`<Rice Grading Dataset Link>`

### Description

This dataset contains **bulk rice images** categorized into quality grades:

- Premium
- Grade 1
- Grade 2
- Grade 3
- Grade 4

Each image contains multiple rice grains representing real-world rice samples.

---

## 4️⃣ YOLOv8 Detection Dataset

**🔗 Dataset:**  
`<YOLO Annotation Dataset Link>`

### Description

Approximately **1,200 bulk rice images** were manually annotated with bounding boxes for individual rice grains and impurities.

This dataset was used to train the **YOLOv8 Rice Detection Model**.

---

## 5️⃣ Real-Time Dataset

Around **50 real rice images** were captured under different lighting conditions and augmented to approximately **200 images** for evaluation and deployment testing.

---

# 🧠 Model Architecture

The framework consists of three independent deep learning models.

---

## 🔹 Model 1 – Rice Variety Classification

- Input Size: **224 × 224**
- Classes: **5**
- Optimizer: Adam
- Learning Rate: **3 × 10⁻⁴**
- Loss Function: Sparse Categorical Crossentropy

---

## 🔹 Model 2 – Rice Defect Classification

- Input Size: **224 × 224**
- Classes: **4**
- Optimizer: Adam
- Learning Rate: **3 × 10⁻⁴**
- Loss Function: Sparse Categorical Crossentropy

---

## 🔹 Model 3 – Rice Grain Detection

- YOLOv8 Object Detection
- Bounding Box Localization
- Multi-Grain Detection
- Real-Time Detection

---

### CNN Components

Each CNN consists of:

- Convolution Layers
- ReLU Activation
- MaxPooling Layers
- Dropout Layers
- Flatten Layer
- Dense Layers
- Softmax Output Layer

---

# ⚙️ Methodology

## 1. Data Collection

- Rice Variety Dataset
- Rice Defect Dataset
- Rice Grading Dataset
- YOLO Annotation Dataset
- Real-Time Captured Images

---

## 2. Image Preprocessing

- Dataset Merging
- Dataset Balancing
- Data Augmentation
- Horizontal Flipping
- Rotation
- Image Resizing (224 × 224)
- Normalization

---

## 3. Rice Grain Detection

Two detection approaches were implemented:

### Contour-Based Segmentation

- Grayscale Conversion
- Canny Edge Detection
- Morphological Dilation
- Contour Extraction
- Bounding Box Generation

### YOLOv8 Detection

- Manual Bounding Box Annotation
- Object Detection
- Grain Localization
- Grain Cropping

---

## 4. Feature Learning

The CNN automatically learns:

### Variety Features

- Shape
- Texture
- Grain Structure

### Defect Features

- Broken Grain
- Chalkiness
- Surface Damage
- Discoloration

---

## 5. Model Training

The models were trained using:

- Adam Optimizer
- Dropout Regularization
- Data Augmentation
- Early Stopping
- Model Checkpointing

---

## 6. Model Evaluation

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- mAP@50 (YOLOv8)

---

## 7. Rice Grade Calculation

The quality grade is determined based on the percentage of defective grains.

| Defect Percentage | Grade |
|-------------------|-------|
| 0–5% | Premium |
| 5–10% | Grade 1 |
| 10–20% | Grade 2 |
| 20–30% | Grade 3 |
| >30% | Grade 4 |

---

# 🏗 System Workflow

```text
Bulk Rice Image
        │
        ▼
Image Preprocessing
        │
        ▼
YOLOv8 / Contour Detection
        │
        ▼
Crop Individual Grains
        │
        ├──────────────┐
        ▼              ▼
 Variety CNN      Defect CNN
        │              │
        └──────┬───────┘
               ▼
Defect Percentage Calculation
               ▼
 Rice Grade Assignment
               ▼
 Streamlit Web Application
               ▼
 Final Prediction
```

---

# 💻 Tech Stack

- Python
- TensorFlow
- Keras
- YOLOv8 (Ultralytics)
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Streamlit

---

# 📁 Project Structure

```text
project/
│
├── app.py
├── requirements.txt
├── README.md
│
├── models/
│   ├── variety_cnn_model.h5
│   ├── defect_cnn_model.h5
│   └── yolov8_best.pt
│
├── datasets/
│   ├── RiceVariety/
│   ├── RiceDefect/
│   ├── RiceGrading/
│   └── YOLO/
│
├── notebooks/
│
├── utils/
│
└── assets/
```

---

# 🚀 Installation

## Clone Repository

```bash
git clone https://github.com/your-username/project-name.git
cd project-name
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Run the Application

```bash
streamlit run app.py
```

---

# 📌 Applications

- Rice Quality Inspection
- Food Processing Industries
- Agricultural Automation
- Smart Farming
- Quality Control in Rice Mills
- Rice Export Quality Assessment

---

# 🔮 Future Scope

- Detection of additional rice defects and impurities
- Mobile application deployment
- Edge AI implementation
- Cloud-based quality monitoring
- Integration with IoT-enabled sorting systems
- Explainable AI (XAI) for grain classification

---

# 👨‍💻 Authors

- **G. Praveenkumar**
- **V. Mounidharan**
- **P. J. Purushothaman**

### Faculty Mentor

**Dr. A. Divya**  
Assistant Professor (Sr. Gr.)  
Department of Electronics Engineering  
Madras Institute of Technology (MIT Campus)  
Anna University, Chennai

---

# 🙏 Acknowledgements

The authors sincerely thank the **Department of Electronics Engineering, Madras Institute of Technology, Anna University**, **Dr. A. Divya**, and the contributors of the publicly available rice grain datasets used in this research.

---

# 📜 License

This project has been developed for **academic and research purposes only**.

The datasets used remain the property of their respective authors and are subject to their respective licenses and terms of use.

---

⭐ **If you found this project useful, consider giving it a Star!**
