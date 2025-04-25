# Face Verification Using Siamese Network

This project implements a **real-time face verification system** using a Siamese Neural Network. Instead of identifying who a person is, the system verifies whether two given face images belong to the same individual. This project covers data collection, model training, evaluation, and a live webcam-based verification system.

---

## 🔍 Project Overview
- **Type:** Deep Learning (One-shot Learning)
- **Model:** Siamese Neural Network with a shared CNN
- **Objective:** Verify if two face images are of the same person
- **Frameworks Used:** TensorFlow, Keras, OpenCV
- **Development Environment:** Jupyter Notebook

---

## 📊 Project Workflow

### 1. **Data Collection and Preprocessing**
- Images are collected and paired as **positive (same person)** and **negative (different people)**.
- All images are resized to a uniform size.
- Data augmentation is optionally used to improve generalization.

### 2. **Model Architecture**
- A **single CNN** is used as a feature extractor and shared between both image inputs.
- The two images are passed through the same CNN to extract embeddings.
- Embeddings are compared using the **absolute difference**.
- The result passes through a Dense layer with a **sigmoid activation** to output similarity probability.

### 3. **Loss Function and Optimizer**
- **Binary Crossentropy** is used for loss calculation.
- **Adam Optimizer** is used to update model weights.

### 4. **Training Loop**
- Implemented using a custom training loop with `tf.GradientTape`.
- Metrics tracked per epoch include **loss**, **precision**, and **recall**.
- Model checkpoints are saved every 10 epochs.

### 5. **Evaluation**
- **Training Loss**: Decreases steadily over epochs.
- **Precision**: Initially fluctuates due to few positive predictions, stabilizes above 99%.
- **Recall**: Approaches 100% quickly and remains consistent.
- Precision and recall graphs are plotted using Matplotlib.

### 6. **Live Face Verification**
- A webcam-based system captures a real-time face frame.
- The captured frame is compared against a reference image.
- Uses OpenCV for real-time face detection and preprocessing.
- Displays result: **"Verified"** or **"Not Verified"** on screen.

---
