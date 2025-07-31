# 🦯 Blind Assistance System 

A real-time object detection and spatial awareness system for visually impaired individuals. The system uses computer vision and audio feedback to help users understand their surroundings.

## ✨ Features

-🎯 Real-time object detection using YOLOv8
-📏 Distance measurement and spatial awareness
- 🗣️Natural voice feedback with distance announcements
- 📺Real-time visual display with detection information
- 🔊Priority-based object announcement system
- ↔️Detailed position information (left, right, or directly ahead)
- 📐Distance measurements in feet or meters
- ⚙️Configurable settings for personalization

## 💻Requirements

- Python 3.8 or higher
- Webcam or compatible camera device
- CUDA-capable GPU recommended (but not required)
- Quality speakers or headphones
- Display for visual feedback (optional)

## 🛠️ Installation

1. 📦Clone the repository:
bash
git clone https://github.com/yourusername/blind-assistant.git
cd blind-assistant


2.🧪 Create a virtual environment (recommended):
bash
python -m venv venv
# On Windows:
venv\Scripts\activate
# On Linux/Mac:
source venv/bin/activate


3. 📥 Install dependencies:
bash
pip install -r requirements.txt


4. 🎯 Download YOLOv8 weights:
bash
mkdir weights
# Download YOLOv8n weights
wget https://github.com/ultralytics/assets/releases/download/v0.0.0/yolov8n.pt -O weights/yolov8n.pt


## 🔈 Audio System Setup

Before running the main application, test your audio system:

1. Run the audio test utility:
bash
python test_audio.py


This will:
- Check your system's text-to-speech capabilities
- Display available voices
- Test different speech rates and volumes
- Provide troubleshooting information if needed

### 🛠️ Audio Troubleshooting

If the audio test fails:

#### 🪟 Windows:
1. Check Windows Speech Settings:
   - Open Windows Settings -> Time & Language -> Speech
   - Ensure a speech language is installed
   - Try selecting a different voice

2. Reinstall pyttsx3:
bash
pip uninstall pyttsx3
pip install pyttsx3


#### 🐧 Linux:
1. Install espeak:
bash
sudo apt-get update
sudo apt-get install espeak


2. Test espeak directly:
bash
espeak "This is a test"


#### 🍎 macOS:
1. Check System Preferences -> Accessibility -> Speech
2. Ensure a voice is selected and working

#### 🔁 General Steps:
1. Check system volume and unmute if necessary
2. Verify speakers/headphones are connected and working
3. Try a different voice in the system settings
4. Check if other applications can play audio

## ⚙️ Configuration

Edit config/settings.yaml to customize:

### 🎥 Camera Settings
- Resolution and FPS
- Device selection

### 🔊 Audio Settings
- Voice rate and volume
- Announcement interval
- Distance unit (feet/meters)
- Language selection

### 🎯Detection Settings
- Priority objects
- Maximum objects to announce
- Distance thresholds
- Confidence thresholds

## ▶️ Usage

1.🔁 Activate your virtual environment if not already active

2.🖥️ Basic usage with GUI display:
bash
python src/main.py


3. 🐞 With debug logging enabled:
bash
python src/main.py --debug


4. 🔇 Run without GUI display (audio only):
bash
python src/main.py --no-gui


🧾 Command line arguments:
- --config: Specify a custom configuration file path
- --debug: Enable detailed debug logging
- --no-gui: Disable the visual display window

##🖼️  Visual Display

The GUI window shows:
- 🎥Live camera feed
- 🟥Bounding boxes around detected objects
- 🎯Object class labels with confidence scores
- Distance measurements
- Directional information

⏹️Controls:
- Press 'q' to quit the application
- Press Ctrl+C in terminal to exit

##🗣️ Audio Feedback System

The system provides natural voice feedback about:
- 🔍Object type (person, car, chair, etc.)
- 📏Distance to object (in feet or meters)
- 🗂️Directional information (left, right, or directly ahead)

Examples of announcements:
- "Person directly ahead, 5 feet away"
- "Chair to your left, 2 meters away"
- "Door to your right, 10 feet away"

##🐛Debug Mode

When running with --debug, the system provides detailed logging about:
- 🔍Object detections and their confidence scores
- 📏Distance measurements
- 🗂️System status and processing information
- ⏱️Audio announcement queuing and timing

## 🧩 Common Issues and Solutions

1.❌ No audio output:
   - Run python test_audio.py to diagnose audio issues
   - Check system volume and audio device settings
   - Try different TTS voices in system settings
   - Reinstall pyttsx3 with pip install --upgrade pyttsx3

2.📸 Camera issues:
   - Verify camera connections
   - Check device_id in settings.yaml
   - Ensure no other application is using the camera

3.🎯 Detection issues:
   - Verify YOLO weights are downloaded correctly
   - Check GPU availability and settings
   - Adjust confidence thresholds in settings.yaml

4.🐢 Performance issues:
   - Enable frame skipping in settings.yaml
   - Lower camera resolution
   - Use a more powerful GPU if available

## ⚠️ Safety Notes

- ❗This system is designed as an assistive tool and should not be relied upon as the sole means of navigation
- 🧪Always use traditional mobility aids (white cane, guide dog) alongside this system
- 🧪Test the system in a safe environment before using it in real-world situations
- 📏 The system's distance measurements are approximate and should be used as guidance only

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄License

This project is licensed under the MIT License - see the LICENSE file for details.
