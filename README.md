# Hand Gesture Controlled Mouse

This project demonstrates a hand gesture-controlled mouse using a combination of OpenCV, MediaPipe, and Python libraries. The application captures real-time video from the webcam, detects hand landmarks, and interprets specific gestures to control mouse movements and perform various actions like clicks, double-clicks, screenshots, and adjusting screen brightness.

## Features
- **Mouse Movement**: Control the mouse pointer by moving your hand.
- **Left Click**: Perform a left click gesture.
- **Right Click**: Perform a right click gesture.
- **Double Click**: Perform a double click gesture.
- **Screenshot**: Capture the screen with a specific hand gesture.
- **Brightness Control**: Adjust screen brightness using hand gestures.

## Prerequisites
- Python 3.13
- OpenCV
- MediaPipe
- PyAutoGUI
- Pynput
- Screen Brightness Control
- NumPy

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/hand-gesture-mouse.git
    ```

2. Navigate to the project directory:
    ```bash
    cd hand-gesture-mouse
    ```

3. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

1. Run the main script:
    ```bash
    python main.py
    ```

2. A window will open displaying the webcam feed. Use hand gestures to control the mouse and interact with the screen.

3. Press `q` to exit the application.

## How It Works

### Hand Detection
- The application uses MediaPipe's Hand solution to detect and track hand landmarks in real-time.
- The landmarks are processed to determine finger positions and gestures.

### Gesture Interpretation
- **Mouse Movement**: The index finger tip coordinates are used to move the mouse pointer.
- **Left Click**: Detected when specific angles between finger landmarks are recognized.
- **Right Click**: Similar to left click but with different landmark angles.
- **Double Click**: Combination of gestures to trigger a double-click.
- **Screenshot**: A specific gesture saves a screenshot with a unique filename.
- **Brightness Control**: Adjusting brightness based on the distance between finger landmarks.

## Code Overview

### `main()`
- Initializes the webcam and starts the video capture.
- Processes each frame to detect hand landmarks and interprets gestures using `detect_gesture()`.

### `detect_gesture()`
- Handles various gestures and calls corresponding functions to perform mouse actions or other features.

### Helper Functions
- `find_finger_tip()`: Finds the index finger tip coordinates.
- `move_mouse()`: Moves the mouse pointer based on the detected coordinates.
- `is_left_click()`, `is_right_click()`, `is_double_click()`, `is_screenshot()`, `is_brightness()`: Functions to detect specific gestures.
- `get_distance2()`: Calculates the distance between two landmarks to assist in brightness control.

## Dependencies

- `cv2`: OpenCV for video capture and processing.
- `mediapipe`: MediaPipe for hand detection and tracking.
- `pyautogui`: PyAutoGUI for controlling the mouse and taking screenshots.
- `pynput`: Pynput for controlling mouse clicks.
- `screen_brightness_control`: For adjusting screen brightness.
- `numpy`: For numerical operations.

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request for improvements.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments

- MediaPipe for their robust hand tracking solution.
- OpenCV for video processing capabilities.
- The open-source community for their invaluable contributions.
