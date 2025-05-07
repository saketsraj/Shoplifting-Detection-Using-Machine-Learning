# 🛒 Shoplifting Detection using Machine Learning

A real-time intelligent surveillance system that detects suspicious human behavior (e.g., shoplifting) in retail stores using live video feeds, pose estimation, and machine learning.

---

## 📌 Overview

This system:
- Detects humans using **YOLOv8**.
- Estimates human poses via keypoint tracking.
- Analyzes behavior using an **XGBoost** classifier.
- Sends alert emails if suspicious activity is detected.
- Logs and records output video with annotations.

> 📍 Main script: `live_detectionOne.ipynb` (Jupyter Notebook for better visualization and experimentation)

---

## 🎯 Features

- 👤 Real-time human detection and tracking
- 🕵️ Suspicious activity detection using behavior analysis
- 📩 Email alerts with screenshot attachments
- 💾 Saves output video logs
- 🧪 Tested with sample CCTV footage from retail environments

---

## 🧠 Methodology

### 🔴 1. **Live Video Input**
Captured using a connected webcam or IP/CCTV feed.

### 🟡 2. **Object Detection (YOLOv8)**
Detects humans in real-time (~30 FPS) and extracts 17 keypoints for each person.

### 🟢 3. **Behavioral Analysis (XGBoost)**
- Trained on hand motion, body orientation, and proximity to shelves.
- Classifies actions as:
  - **Normal (1)** – Shopper behavior
  - **Suspicious (0)** – Possible shoplifting activity

### 🔔 4. **Alert System**
- Sends email with frame attachment using Gmail SMTP if suspicious behavior is detected.
- Cooldown logic avoids spamming the inbox.

---

## 🗃️ Directory Structure

Shoplifting-Detection/
├── test_videos/ # CCTV test footage
├── output_video/ # Annotated output logs (auto-generated)
├── model_weights.json # Trained XGBoost model
├── best.pt # YOLOv8 custom-trained weights
├── live_detectionOne.ipynb # ⚙️ Main script (run in Jupyter)
├── utils/ # Helper scripts (email, preprocessing)
├── requirements.txt
└── README.md
