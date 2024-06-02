# VibroVision

VibroVision is an intelligent user interface application designed for providing haptic feedback based on object detection in the classic game Super Mario Bros. The application uses a custom-trained YOLOv8 model to detect objects in the game and triggers corresponding haptic feedback using a Bhaptics TactSuit.

## Course Information

- **Course**: COMP 537 Intelligent User Interfaces
- **Term**: Spring 2024
- **Institution**: Koç University

## Project Structure

```
VibroVision/
├── assets/
│   ├── games/
│   ├── icons/
│   ├── models/
│   │   └── yolov8m_vibrovision.pt
│   └── tacts/
├── main.py
└── requirements.txt
```

## Requirements

Make sure you have the following dependencies installed. You can install them using the `requirements.txt` file.

```sh
pip install -r requirements.txt
```

### `requirements.txt`

```
numpy==1.26.4
pygetwindow==0.0.9
opencv-python==4.9.0.80
ultralytics==8.2.2
websocket-client==1.8.0
pyautogui==0.9.54
PyQt5==5.15.10
torch==2.2.2
```

## Usage

### Running the Application

1. **Navigate to the project directory**:
    ```sh
    cd /path/to/VibroVision
    ```

2. **Run the application**:
    ```sh
    python main.py
    ```

### Application Overview

The application provides a graphical user interface (GUI) with several tabs:

1. **Library Tab**: Allows you to select a game (currently supports Super Mario Bros).
2. **Interactions Tab**: Lets you configure haptic feedback interactions based on in-game events.
3. **Capture Tab**: Allows you to select a window to capture and process screenshots.
4. **Settings Tab**: Lets you adjust application settings such as haptic feedback intensity.

### Core Functionalities

- **Object Detection**: Uses a custom-trained YOLOv8 model to detect objects in the game.
- **Haptic Feedback**: Sends haptic feedback signals to the Bhaptics TactSuit based on detected interactions.
- **Screenshot Capture**: Captures and processes screenshots from the selected game window.

## Code Overview

### BhapticsManager Class

Manages the connection and communication with the Bhaptics TactSuit, including registering and submitting haptic feedback.

### YOLOModel Class

Handles the object detection using a custom-trained YOLOv8 model. It predicts objects in the provided screenshots and returns their bounding boxes, confidence scores, and class labels.

### ScreenCapture Class

Handles the capturing of screenshots from a specified window.

### VibroVisionApp Class

The main application class that initializes the GUI, handles user interactions, and integrates all functionalities (object detection, haptic feedback, and screenshot capture).