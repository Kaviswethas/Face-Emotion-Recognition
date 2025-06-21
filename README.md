# 🧠 Face Emotion Recognition

This project uses a webcam to detect human faces and recognize their emotions in real time using deep learning. It leverages OpenCV for video capture and the facial_emotion_recognition library (based on PyTorch) to classify emotions like happy, sad, angry, surprise, and more.

# 🔧 Features

- Real-time face detection from webcam
- Emotion recognition using pre-trained deep learning model
- Runs on CPU (no GPU required)

# 🚀 Requirements

- Python 3.6+
- OpenCV
- torch
- facial_emotion_recognition

# 📦 Installation

Run the following command in your terminal
Bash

pip install facial-emotion-recognition
pip install opencv-python torch

⚠️ Note: 
> The Custom Modification mentioned below is only possible after installing the facial_emotion_recognition library.  
> Please install it first using pip install facial-emotion-recognition, then apply the changes in the installed package files.


# 🛠️ Custom Modification

To make the project work correctly on CPU-only systems, a small change is needed in the facial_emotion_recognition.py

## 📁 File to modify:
File Path looks like C:\Users\user\AppData\Local\Programs\Python\Python39\Lib\site-packages\facial_emotion_recognition\facial_emotion_recognition.py

If you could't find it :
- press windows key, search for IDLE
- right click on IDLE
- select open file location
- you can find the IDLE
- Now again right click on the IDLE
- select open file location
- Now find the Lib file and enter into the file
- find the site-packages file and enter into it
- Now get into the facial_emotion_recognition file
- now you can see the facial_emotion_recognition.py file

Open the facial_emotion_recognition.py file

## 🔄 Replace this line:

Python

model_dict = torch.load(os.path.join(os.path.dirname(__file__), 'model', 'model.pkl'))

## ✅ With this line:

Python

model_dict = torch.load(os.path.join(os.path.dirname(__file__), 'model', 'model.pkl'), map_location=torch.device('cpu'))
# 🏁 Steup Completed

🎉 With this setup, you now have a working Real-Time Face Emotion Recognition system running on your webcam — no GPU needed!
