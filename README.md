# ball-tracking
# Orange Ball Tracking with Raspberry Pi and Servomotors

This project demonstrates how to use a Raspberry Pi 4, Pi Camera, and two servomotors to track and follow an orange ball. The servomotors control the camera's movement to keep the ball centered in the frame. The project uses OpenCV for image processing and object tracking.

## Project Overview

This system captures live video from the Pi Camera, processes the video stream using OpenCV to detect an orange ball, and adjusts the camera's orientation using servomotors to follow the ball's movement. It uses color-based detection (HSV color space) to identify the ball and track its position in real-time.

## Hardware Requirements

- **Raspberry Pi 4** (or any model with camera support)
- **Pi Camera Module** (v2 or compatible)
- **2 Servo Motors** (for controlling the camera's movement)
- **Power Supply** for Raspberry Pi and servomotors
- **Jumper wires** for connecting servomotors to GPIO pins
- **Optional**: A video file for testing

## Software Requirements

- **Python 3.x**
- **OpenCV** (for image processing)
- **imutils** (for resizing and handling video streams)
- **numpy** (for array operations)

## Installation Guide

### 1. Setup Raspberry Pi

- Set up your Raspberry Pi and ensure it has the latest updates:
  ```bash
  sudo apt-get update && sudo apt-get upgrade

Attach the Pi Camera Module to the CSI interface on the Raspberry Pi.

2. Install Dependencies
Install the necessary libraries by running the following commands:

bash
Copy
sudo apt-get install python3-opencv
pip3 install imutils numpy
3. Clone the Repository
Clone this repository to your Raspberry Pi:

bash
Copy
git clone https://github.com/yourusername/ball-tracking.git
cd ball-tracking
4. Run the Python Script
To start tracking the orange ball, run the following command:

bash
Copy
python3 ball_tracking_orange.py
If you want to test with a video file instead of the live camera stream, use the --video option:

bash
Copy
python3 ball_tracking_orange.py --video path/to/video.mp4
5. Adjusting the Camera Movement (Optional)
Ensure that the servomotors are correctly wired to the Raspberry Pi GPIO pins to adjust the camera’s orientation. Modify the script if necessary to match the GPIO pin configuration of your setup.

How It Works
Capture Video: The Pi Camera (or a video file) captures frames continuously.

HSV Color Detection: The script converts each frame into the HSV color space and applies a mask to isolate the orange color.

Contour Detection: It finds the contours of the orange ball and calculates its centroid.

Tracking Points: The system maintains a list of tracked points, visualizing the path of the ball as it moves.

Servomotor Adjustment: The servomotors adjust the camera’s position to keep the ball centered in the frame.

Customization
HSV Color Range: You can adjust the orangeLower and orangeUpper values to track a different color by tweaking the HSV range.

Camera Source: By default, the script uses the Pi Camera (src=1). If you're using a USB camera or a different video source, change it to src=0.

Troubleshooting
Camera Not Working: Ensure the camera module is enabled in the Raspberry Pi settings (sudo raspi-config).

Servo Motors Not Moving: Check the GPIO pin connections and the servo library initialization.

Future Enhancements
Add a user interface to visualize the ball's position in real-time.

Implement advanced tracking algorithms for more complex movements or objects.

License
This project is licensed under the MIT License - see the LICENSE file for details.

Acknowledgements
OpenCV: For the computer vision processing.

imutils: For convenient image processing utilities.

Raspberry Pi Foundation: For providing the Pi Camera and hardware.

Feel free to contribute to this project by forking it, submitting issues, or creating pull requests. Happy tracking!
