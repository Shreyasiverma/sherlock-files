# 🕵️‍♂️ Project Sherlock: Video Temporal Restoration

**Project Sherlock** is an AI-powered digital forensic tool developed for the **MLWare '26 Sherlock Files** competition. The system is designed to solve the "Temporal Puzzle"—reconstructing the original chronological order of shuffled video frames using Deep Learning.

## 📌 Overview
In digital forensics, video files recovered from corrupted storage often lose their temporal integrity. **Sherlock** utilizes a hybrid architecture to analyze visual cues and motion dynamics to reorder these frames and restore the original timeline of events.

## 🚀 Key Features
* **Hybrid Architecture:** CNNs for spatial features + Transformers for temporal logic.
* **Ordinal Ranking:** Predicts the precise rank/position of each frame.
* **Forensic Accuracy:** Uses **Kendall Tau ($\tau$) Coefficient** for evaluation.
* **Lightweight:** Optimized for quick reconstruction (~90MB model size).

## 🧠 Technical Architecture
1. **Feature Extraction:** A **ResNet-34** backbone extracts high-dimensional spatial features.
2. **Sequence Modeling:** A **Transformer Encoder** analyzes the relationship between frames.
3. **Ranking Head:** A linear layer outputs scores to determine the final sequence.

## 📊 Performance
* **Private Score:** `0.0858` (Kendall Tau)
* **Parameters:** ~23 Million
* **Optimizer:** AdamW with Cosine Annealing
* **Hardware:** Tesla P100 GPU

## 🛠️ Tech Stack
* **Language:** Python
* **Frameworks:** PyTorch, Torchvision
* **Tools:** OpenCV, NumPy, Pandas, Matplotlib

## 📝 How It Works
1. **Input:** A set of shuffled frames from a video clip.
2. **Preprocessing:** Frames are resized to 128x128 and normalized.
3. **Prediction:** The model assigns a "temporal score" to each frame.
4. **Output:** Frames are sorted based on scores to recreate the seamless video.

## 🚀 Future Scope
* Integration of **3D-CNNs** for better motion analysis.
* Development of a **Streamlit Web Interface** for forensic uploads.
