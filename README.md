# 🎭 Multi-Face Emotion Detection Using CNN Tiny Face Detector

> Real-time multi-face emotion recognition system designed for classroom learning environments.  
> **Published Academic Journal** · Institut Bisnis dan Informatika Kwik Kian Gie · 2026

---

## 📋 Abstract

This study presents a real-time multi-face emotion detection system designed for classroom learning environments. The system integrates a **CNN-based Tiny Face Detector** for multi-scale face localization with a convolutional neural network for emotion classification into seven categories: *angry, disgust, fear, happy, sad, surprise, and neutral*.

Experimental evaluation was conducted using classroom video streams under varying lighting conditions, face orientations, occlusions, and multiple face appearances per frame. The system achieved stable real-time performance with frame rates ranging from **10–20 FPS**, depending on the number of detected faces.

---

## 🎯 Key Results

| Metric | Value |
|--------|-------|
| Overall Accuracy | **>70%** (aggregated over multiple faces & time windows) |
| Best Classification Confidence | **Up to 91%** (Happy & Surprise) |
| Real-time Performance | **10–20 FPS** depending on face count |
| Emotion Classes | **7** (Angry, Disgust, Fear, Happy, Sad, Surprise, Neutral) |
| FPS with 1–2 faces | ~18–20 FPS |
| FPS with 4–5 faces | ~11–14 FPS |

---

## 🧠 Emotion Detection Performance

| Emotion | Confidence Level | Detection Difficulty |
|---------|-----------------|----------------------|
| 😊 Happy | ~91% | ⭐ Easiest |
| 😲 Surprise | ~90% | ⭐ Easy |
| 😐 Neutral | ~75–85% | ⭐⭐ Moderate |
| 😠 Angry | ~75–80% | ⭐⭐ Moderate |
| 😢 Sad | ~65–75% | ⭐⭐⭐ Difficult |
| 🤢 Disgust | ~65–75% | ⭐⭐⭐ Difficult |
| 😨 Fear | ~65–75% | ⭐⭐⭐ Most Difficult |

---

## 🔧 Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-27338e?style=for-the-badge&logo=OpenCV&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)

- **Face Detection:** CNN-based Tiny Face Detector (multi-scale feature aggregation)
- **Emotion Classification:** Convolutional Neural Network (CNN)
- **Dataset:** FER-2013 (7 emotion classes, 35,000+ images)
- **Language:** Python
- **Libraries:** OpenCV, TensorFlow/Keras, NumPy

---

## 🏗️ System Architecture

```
Input (Camera / Video)
        │
        ▼
┌─────────────────────────┐
│   Data Acquisition      │  RGB Camera + FER-2013 Dataset
└────────────┬────────────┘
             │
             ▼
┌─────────────────────────┐
│  Multi-Face Detection   │  CNN-based Tiny Face Detector
│  D(x) = argmax g_φ(x_b)│  Multi-scale feature aggregation
└────────────┬────────────┘
             │
             ▼
┌─────────────────────────┐
│  Emotion Classification │  CNN Classifier
│  ŷ = argmax h_θ(F_k)   │  7-class emotion recognition
└────────────┬────────────┘
             │
             ▼
┌─────────────────────────┐
│ Visualization & Output  │  Emotion Dashboard & Metrics
│  E_k = (n_k / Σn_i)×100│  Aggregated emotion distribution
└─────────────────────────┘
```

---

## 📊 Research Methodology

### 1. Data Acquisition
- Classroom video collected using standard RGB cameras
- Supplemented with **FER-2013** public dataset for model training
- Various lighting conditions, face orientations, and distances

### 2. Multi-Face Detection
The face detection function is formulated as:

$$D(x) = \arg\max_{b \in B} \{g_\phi(x_b)\}$$

Where $x_b$ is an image patch for bounding box $b$, $B$ is the set of candidate regions across image scales, and $g_\phi$ is the CNN detection function.

### 3. Emotion Classification
Seven emotions classified using:

$$\hat{y} = \arg\max_k \{h_\theta(F_k)\}$$

### 4. Emotion Distribution Analysis
Aggregated emotion output across multiple faces:

$$E_k = \frac{n_k}{\sum_{i=1}^{C} n_i} \times 100\%$$

---

## 🎬 Demo

| Detection Example | Description |
|:-----------------:|-------------|
| 🔴 Red bounding box | Angry emotion detected |
| 🟡 Yellow bounding box | Happy emotion detected |
| 🟠 Orange bounding box | Fear emotion detected |
| 🔵 Blue bounding box | Sad emotion detected |
| 🟣 Pink bounding box | Disgust emotion detected |

---

## 🚀 How to Run

```bash
# Clone repository
git clone https://github.com/marcomarcheleno/Face_Emotion_Detection_Using_CNN.git
cd Face_Emotion_Detection_Using_CNN

# Install dependencies
pip install -r requirements.txt

# Run real-time detection (webcam)
python main.py --mode webcam

# Run on video file
python main.py --mode video --input your_video.mp4
```

---

## 📁 Project Structure

```
Face_Emotion_Detection_Using_CNN/
│
├── main.py                  # Main entry point
├── detector/
│   ├── face_detector.py     # Tiny Face Detector implementation
│   └── emotion_classifier.py # CNN emotion classification model
├── models/
│   └── emotion_model.h5     # Trained CNN model weights
├── utils/
│   └── visualizer.py        # Bounding box & dashboard rendering
├── requirements.txt
└── README.md
```

> ⚠️ *Note: The project structure above reflects the intended architecture. Code files will be uploaded progressively.*

---

## 👥 Authors

| Name | Student ID | Institution |
|------|-----------|-------------|
| Jason Istioso | 55230252 | Kwik Kian Gie School of Business and Informatics |
| Jeremiah Gerard | 55230126 | Kwik Kian Gie School of Business and Informatics |
| **Marco Marcheleno** | 59230168 | Kwik Kian Gie School of Business and Informatics |
| Muhammad Akbar Maulana | — | Kwik Kian Gie School of Business and Informatics |

---

## 📄 Publication

This project was published as an academic journal at **Institut Bisnis dan Informatika Kwik Kian Gie (2026)**.

> **"Multi-Face Emotion Detection Using CNN Tiny Face Detector"**  
> Jason Istioso, Jeremiah Gerard, Marco Marcheleno, Muhammad Akbar Maulana  
> Program Studi Teknik Informatika, Institut Bisnis dan Informatika Kwik Kian Gie · 2025/2026

📎 [Full Paper — Published in JURTEKSI](https://jurnal.stmikroyal.ac.id/index.php/jurteksi/article/view/4354/2189) · [Research Report (PDF)](./LaporanPenelitianTinyFaceEmotionDetector-2.pdf)

---

## 📚 References

Key references used in this research:

1. Pereira et al. — *Systematic Review of Emotion Detection with Computer Vision and Deep Learning*, Sensors 2024
2. Krizhevsky, Sutskever & Hinton — *ImageNet Classification with Deep CNNs*, ACM 2017
3. Wu, Peng & Yu — *YuNet: A Tiny Millisecond-level Face Detector*, Machine Intelligence Research 2023
4. Minaee et al. — *Deep-Emotion: Facial Expression Recognition Using Attentional CNN*, Sensors 2021

---

## 📜 License

This project is for academic purposes. Please cite the authors if you use this work as a reference.

---

<p align="center">
  Made with ❤️ for classroom AI monitoring research
  <br>
  Institut Bisnis dan Informatika Kwik Kian Gie · 2026
</p>
