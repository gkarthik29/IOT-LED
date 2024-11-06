# Hand Gesture Controlled LED with OpenCV, MediaPipe, and Arduino
Control an LED's brightness using hand gestures detected by a webcam. This project utilizes Python, OpenCV, and MediaPipe for gesture recognition, and Arduino for LED control via PWM signals.
![Python](https://img.shields.io/badge/Python-3.6%2B-blue)
![Arduino](https://img.shields.io/badge/Arduino-Compatible-orange)
## Table of Contents
- [Features](#features)
- [Requirements](#requirements)
- [Setup](#setup)
- [Usage](#usage)
- [Code Overview](#code-overview)
- [Troubleshooting](#troubleshooting)
## Features
- Real-time hand gesture detection
- Adjustable LED brightness based on finger distance
- Easily adaptable for other gesture-controlled outputs
## Requirements

### Hardware
- Arduino board (any model supporting PWM)
- LED and a 220Ω resistor
- USB cable
- Webcam

### Software
- **Python** 3.6 or higher
- Libraries: `opencv-python`, `mediapipe`, `pyfirmata2`

Install dependencies:
```bash
pip install opencv-python mediapipe pyfirmata2

```
**Setup Instructions**

Walk users through setting up their Arduino, connecting the hardware, and configuring the port. Make sure to provide clear steps.


## Setup

1. **Arduino Setup**:
   - Connect an LED to Arduino's **pin 3** with a resistor.
   - Upload the **StandardFirmata** sketch to the Arduino:
     - Open Arduino IDE.
     - Go to **File > Examples > Firmata > StandardFirmata**.
     - Upload the sketch.

2. **Python Setup**:
   - Update the `COM3` port in the script if necessary.
   - Run the script using `python hand_gesture_led_control.py`.
## Usage
1. Run the script:
   ```bash
   python hand_gesture_led_control.py

## Code Overview

Explain the main code functions and structure. This section is useful for developers who want to understand or modify the code.



```bash
- **OpenCV** captures video from the webcam.
- **MediaPipe** detects hand landmarks and calculates the thumb-index distance.
- **PyFirmata** sends PWM signals to Arduino, adjusting LED brightness.

Key code segments:
- `mp_hands.Hands()`: Initializes the hand tracker.
- `distance = math.sqrt(...)`: Calculates distance between thumb and index finger.
- `ledPin.write(...)`: Controls LED brightness based on calculated distance.
```
## Troubleshooting

- **Webcam Not Detected**: Ensure it’s connected and try restarting the script.
- **Arduino Not Recognized**: Verify the port (e.g., `COM3`) and that the Firmata sketch is uploaded.
- **LED Behavior Issues**: Adjust the threshold distance in the code.
