# Sign Language Detection Project

## Overview
This project aims to detect sign language gestures in real-time using a deep learning model built with TensorFlow and Mediapipe. It leverages a webcam or an IP camera feed to capture video frames and predicts the corresponding gestures using a trained model. The system visualizes the probabilities of predictions in the video feed, providing an interactive and educational experience.

---

## Features
### Real-Time Sign Language Detection
- Utilizes a pre-trained model for gesture recognition.
- Processes live video feed from a webcam or IP camera using OpenCV.
- Visualizes prediction probabilities using an overlay on the video feed.

### Modular Design
- **Training and Data Collection**:
  - Separate scripts for training (`trainmodel.py`) and data collection (`collectdata.py`).
- **Utilities**:
  - Modularized helper functions in `function.py` for cleaner code organization.
- **Model Handling**:
  - Pre-trained model (`model.h5`) and architecture configuration (`model.json`) for ease of deployment.

### Logging and Debugging
- Logs stored in the `Logs` directory for monitoring training progress and debugging.

---

## Project Structure
```
Sign_Lang/
├── app.py                  # Main application script for real-time detection
├── trainmodel.py           # Script for training the sign language model
├── collectdata.py          # Data collection script for training/evaluation datasets
├── function.py             # Utility functions used across the project
├── data.py                 # Data preprocessing and loading script
├── model.h5                # Trained model weights
├── model.json              # Model architecture configuration
├── Logs/                   # Training and debugging logs
├── MP_Data/                # Intermediate or processed data for training
├── Image/                  # Image resources (e.g., for documentation or training)
├── LICENSE                 # Project licensing terms
├── README.md               # Project documentation (this file)
└── .git/                   # Git repository configuration
```

---

## Prerequisites
- **Python 3.7+**
- Required Libraries:
  - TensorFlow
  - Mediapipe
  - OpenCV
  - Keras

Install dependencies using:
```bash
pip install -r requirements.txt
```

---

## How to Use

### 1. Real-Time Detection
Run the main application:
```bash
python app.py
```
- This will open a webcam feed and start detecting gestures.
- Predictions are visualized in the video feed with confidence levels.

### 2. Collecting Data
To collect new gesture data:
```bash
python collectdata.py
```
- Save new datasets in the `MP_Data` directory for further training.

### 3. Training the Model
Retrain or fine-tune the model:
```bash
python trainmodel.py
```
- Logs of the training process are stored in the `Logs` directory.

---

## Key Functions

### `app.py`
- Loads the pre-trained model (`model.json` and `model.h5`).
- Processes live video feed and predicts gestures.
- Uses `prob_viz` to overlay prediction probabilities on the video feed.

### `trainmodel.py`
- Handles model training with TensorFlow/Keras.
- Saves updated weights and architecture.

### `collectdata.py`
- Captures and stores new data samples for additional gestures.

### `function.py`
- Contains utility functions for processing frames, predictions, and visualization.

---
