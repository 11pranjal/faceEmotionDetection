# Emotion Detection

A real-time emotion detection application that uses computer vision and deep learning to analyze facial expressions from a webcam feed and display corresponding emojis.

## Features

- Real-time face detection using OpenCV
- Emotion classification using a pre-trained Keras model
- Emoji overlay on video feed based on detected emotions
- Web-based interface using Flask
- Support for 7 emotions: Angry, Disgusted, Fearful, Happy, Sad, Surprised, Neutral

## Prerequisites

- Python 3.8 or higher
- Webcam (built-in or external)
- Git (for cloning the repository)

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/11pranjal/faceEmotionDetection.git
   cd emotion-detection
   ```

2. **Create a virtual environment (recommended):**
   ```bash
   python -m venv venv
   ```

3. **Activate the virtual environment:**
   - On Windows:
     ```bash
     venv\Scripts\activate
     ```
   - On macOS/Linux:
     ```bash
     source venv/bin/activate
     ```

4. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

5. **Ensure model files are present:**
   - The project includes `model.keras` (the trained emotion detection model)
   - Emoji images should be in the `emoji/` directory

## Usage

1. **Run the Flask application:**
   ```bash
   python app.py
   ```

2. **Open your web browser and navigate to:**
   ```
   http://localhost:5000
   ```

3. **Click on "Open Camera" to start the emotion detection.**

4. The application will:
   - Access your webcam
   - Detect faces in real-time
   - Predict emotions using the deep learning model
   - Overlay corresponding emojis on the video feed

## How It Works

### Architecture

The application consists of several components:

1. **Face Detection:** Uses OpenCV's Haar cascade classifier to detect faces in the video stream.

2. **Emotion Prediction:** A pre-trained Convolutional Neural Network (CNN) model built with Keras/TensorFlow analyzes facial expressions and classifies them into one of 7 emotions.

3. **Emoji Overlay:** Based on the predicted emotion, the corresponding emoji image is overlaid on the video feed in the top-right corner.

4. **Web Interface:** Flask serves a simple web page that displays the video stream with emotion detection.

### Technical Details

- **Model:** The emotion detection model is a Keras model saved in HDF5 format (`model.keras`).
- **Face Detection:** Utilizes `haarcascade_frontalface_default.xml` from OpenCV for face detection.
- **Emotions:** The model recognizes 7 basic emotions with corresponding emoji representations.
- **Video Processing:** Real-time video capture and processing using OpenCV.
- **Web Framework:** Flask for serving the web application.

### Files Structure

```
emotion-detection/
├── app.py                 # Main Flask application
├── gui.py                 # Desktop GUI version (optional)
├── model.keras           # Trained emotion detection model
├── class.keras           # Alternative model file
├── requirements.txt      # Python dependencies
├── emoji/                # Emoji images for each emotion
├── static/
│   └── style/
│       └── style.css     # CSS styles
├── templates/
│   ├── index.html        # Main page
│   └── open_camera.html  # Camera interface
└── README.md             # This file
```

## Troubleshooting

- **Camera not accessible:** Ensure your webcam is not being used by another application and that you have granted camera permissions.
- **Model loading errors:** Verify that `model.keras` and emoji files are present in the correct directories.
- **Import errors:** Make sure all dependencies are installed correctly in your virtual environment.
- **Port already in use:** If port 5000 is busy, you can change the port in `app.py`.

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- OpenCV for computer vision capabilities
- Keras/TensorFlow for deep learning framework
- Flask for web framework