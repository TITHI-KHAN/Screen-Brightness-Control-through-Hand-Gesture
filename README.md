# Screen-Brightness-Control-through-Hand-Gesture

This Python script utilizes hand tracking with MediaPipe to control screen brightness based on the distance between the thumb tip and the index finger tip. It also provides functionality for adjusting screen brightness using OS-specific brightness control libraries.

Here's a breakdown of the script:

1. It imports necessary libraries including `cv2` for OpenCV, `mediapipe` for hand tracking, and `time` for potential delays or adjustments.

2. OS-specific brightness control libraries are imported. In this case, it uses `win32api` and `win32con` for Windows. If these libraries are not found, a message is printed indicating limited functionality.

3. MediaPipe hands module is initialized for hand tracking.

4. Functions are defined:
   - `map_hand_distance_to_brightness()`: Maps the distance between thumb tip and index finger tip to a brightness value within a specified range.
   - `set_brightness()`: Sets the screen brightness using OS-specific brightness control libraries.

5. Video capture is initialized.

6. Within the main loop:
   - Frames are captured from the webcam and processed using MediaPipe hands.
   - Hand landmarks are detected, and the distance between the thumb tip and index finger tip is calculated.
   - The distance is mapped to a brightness value, and the screen brightness is adjusted accordingly.
   - Hand landmarks are drawn on the frame for visualization.

7. The loop continues until the user exits by pressing the ESC key.

8. Finally, the script releases the video capture and closes all OpenCV windows.

This script demonstrates a practical application of hand tracking, allowing users to control screen brightness with hand gestures. It can be further extended for various interactive applications involving hand gesture recognition. 
