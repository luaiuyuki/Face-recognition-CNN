# Face-recognition-CNN

💻 **Project Overview:** Face recognition system using CNN, FaceNet, and OpenCV (LBPH)

---

## 🧠 Introduction

This project implements a face recognition system using three main methods:

1. **CNN (Convolutional Neural Network):** trained from scratch.  
2. **FaceNet:** creates face embeddings and compares distances.  
3. **OpenCV LBPH:** traditional method using histograms of binary images.

The system can recognize people from:

- Saved video files  
- Live webcam feed

---

## 📁 Project Structure

```text
├── data/
│   ├── train/            # Original videos for training (folders per person)
│   └── video/            # Test videos
│
├── dataset/
│   ├── train/            # Face images extracted from videos (training)
│   └── val/              # Validation data
│
├── notebook/
│   ├── face_recognition_face_net.ipynb     # FaceNet recognition
│   ├── face_recognition_cnn.ipynb          # CNN training & recognition
│   └── face_recognition_LBPH.ipynb         # OpenCV LBPH recognition
│
├── output/
│   ├── output_facenet.mp4
│   ├── output_video_cnn.mp4
│   └── webcam.mp4         # Output video with recognition
│
├── face_cnn_model.keras                # Trained CNN model
├── haarcascade_frontalface_default.xml # OpenCV face detection model
├── label_map.pkl                        # Mapping file between IDs and names
├── trainer.yml                           # LBPH training config (if used)
├── Trump_test.mp4                        # Test input video
└── README.md                             # This README
```

## ⚙️ System Workflow

1. Data Extraction
   - Place videos in data/train/ (separate folders for each person)
   - Faces are automatically extracted and saved into dataset/train/ and dataset/val/

2. Model Training
   - CNN: Train a face classification model from scratch
   - FaceNet: Use pre-trained model to generate face embeddings and compare via cosine or Euclidean distance
   - LBPH: Train using OpenCV's histogram-based face recognition

3. Face Recognition
   - Run on webcam or existing videos
   - Output videos with recognition results are saved in output/

## 🧩 Required Libraries
>                      pip install -r requirements.txt

## Main Libraries
   - opencv-python
   - numpy
   - tensorflow, keras
   - scikit-learn
   - mtcnn or dlib
   - pickle (for saving label map)

## 📌 Notebook Usage
   - face_recognition_face_net.ipynb: Face recognition using FaceNet model
   - face_recognition_cnn.ipynb: CNN-based training and testing
   - face_recognition_LBPH.ipynb: Recognition using OpenCV LBPH

⚠️ Make sure the dataset/ folder and label_map.pkl are prepared in the correct format.

## 📽️ Output
   After execution, output videos are saved in the output/ folder.
