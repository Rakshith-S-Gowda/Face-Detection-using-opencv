# 🧠 Face Detection using OpenCV

This project demonstrates a **real-time face detection system** using
**OpenCV** and **Haar Cascade Classifier**.\
The program captures live video from your webcam, detects faces in the
frame, and highlights them with green rectangles.

------------------------------------------------------------------------

## 🚀 Features

-   Real-time face detection using webcam feed\
-   Haar Cascade Classifier for accurate detection\
-   Lightweight and easy to run on any machine\
-   Press **'A'** key to exit the live video window

------------------------------------------------------------------------

## 🧩 Requirements

Before running the program, make sure you have the following installed:

``` bash
pip install opencv-python
```

------------------------------------------------------------------------

## 📂 Project Structure

    📁 Face-Detection/
    ├── face_detection.py        # Main Python file
    ├── haarcascade_frontalface_default.xml  # Face detection model
    ├── FD.png                   # Sample code screenshot
    ├── Face Detection.jpg       # Output image example
    └── README.md                # Project documentation

------------------------------------------------------------------------

## 💻 How to Run

1.  Clone this repository:

    ``` bash
    git clone https://github.com/yourusername/Face-Detection.git
    ```

2.  Navigate into the project directory:

    ``` bash
    cd Face-Detection
    ```

3.  Run the program:

    ``` bash
    python face_detection.py
    ```

4.  A window will open showing your webcam feed.\
    Detected faces will be marked with green rectangles.\
    Press **'A'** to exit.

------------------------------------------------------------------------

## 🧠 Code Overview

``` python
import cv2

face_cap = cv2.CascadeClassifier("haarcascade_frontalface_default.xml")
video_cap = cv2.VideoCapture(0)

while True:
    ret, video_data = video_cap.read()
    col = cv2.cvtColor(video_data, cv2.COLOR_BGR2GRAY)
    faces = face_cap.detectMultiScale(col, scaleFactor=1.1, minNeighbors=5, minSize=(30,30))
    for (x,y,w,h) in faces:
        cv2.rectangle(video_data, (x,y), (x+w,y+h), (0,255,0), 2)
    cv2.imshow("video_live", video_data)
    if cv2.waitKey(10) == ord("a"):
        break

video_cap.release()
```

------------------------------------------------------------------------

## 📸 Output

### ▶️ Live Face Detection

When you run the program, your webcam feed will open and automatically
detect faces in real time.\
Each detected face is highlighted with a **green rectangle** as shown
below 👇

**🧾 Screenshot of Detection:** 

![Face Detection ](https://github.com/user-attachments/assets/2f365f3c-d139-4c2a-9a2e-d27474e154cc)

------------------------------------------------------------------------

