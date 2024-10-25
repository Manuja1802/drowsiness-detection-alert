
# Real-Time Drowsiness and Yawning Detection System

A real-time application designed to enhance driver safety by detecting drowsiness and yawning using facial landmarks and computer vision. This project helps reduce drowsy driving incidents by providing auditory alerts when signs of fatigue are detected.

## 📝 Project Overview

Drowsy driving is a significant risk factor for road accidents globally. This project provides a solution by monitoring a driver’s eye and mouth movements to identify signs of fatigue, alerting the driver to stay attentive or take necessary breaks. The system is powered by advanced facial landmark detection models, audio alerts, and real-time video analysis.

## 📷 Features

- **Eye Aspect Ratio (EAR) Detection**: Measures eye closure to detect drowsiness.
- **Lip Distance Measurement**: Monitors mouth opening for yawning detection.
- **Real-Time Video Monitoring**: Seamless and efficient video processing to ensure real-time response.
- **Auditory Alerts**: Plays an alarm sound when drowsiness or yawning is detected.

## 🛠️ Technologies & Libraries

- **OpenCV**: For video capture, frame processing, and grayscale conversion.
- **Dlib**: For facial landmark detection using a 68-point facial model.
- **imutils**: Simplifies image processing tasks, such as resizing and frame manipulation.
- **SciPy**: Calculates Euclidean distances for drowsiness and yawning metrics.
- **Pydub**: For audio playback to provide auditory alerts when fatigue is detected.

## 🔍 Algorithms

### Eye Aspect Ratio (EAR)
The Eye Aspect Ratio (EAR) algorithm calculates the ratio of distances between vertical and horizontal eye landmarks to detect prolonged eye closure, indicating drowsiness.

Formula:
\[
EAR = \frac{{\text{{distance}}(p2, p6) + \text{{distance}}(p3, p5)}}{2 \times \text{{distance}}(p1, p4)}
\]

Threshold values:
- `EYE_AR_THRESH`: Threshold below which EAR indicates eye closure.
- `EYE_AR_CONSEC_FRAMES`: Number of consecutive frames with a low EAR to trigger an alert.

### Lip Distance
Measures the distance between the upper and lower lip landmarks to detect yawning, with a set threshold to differentiate normal behavior from yawning.

## 📁 File Structure

- `main.py`: Main code file containing the real-time monitoring logic.
- `haarcascade_frontalface_default.xml`: Pre-trained model for face detection.
- `shape_predictor_68_face_landmarks.dat`: Model for facial landmark detection.
- `alarm.wav`: Audio file for the alarm sound.
- `README.md`: Project documentation (this file).

## 🚀 Getting Started

### Prerequisites

- Python 3.x
- Install the required packages:
  ```bash
  pip install opencv-python dlib imutils scipy pydub
  ```

### Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/Real-Time-Drowsiness-Detection.git
   cd Real-Time-Drowsiness-Detection
   ```

2. Add the `shape_predictor_68_face_landmarks.dat` file (see [Dlib’s model page](https://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2)).

3. Run the project:
   ```bash
   python main.py --webcam 0 --alarm alarm.wav
   ```

4. Press `q` to exit the application.

### Command Line Arguments

- `--webcam`: Specifies the index of the webcam (default is 0).
- `--alarm`: Specifies the path to an alarm .wav file.
