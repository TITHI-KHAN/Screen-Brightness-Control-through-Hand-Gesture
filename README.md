# Screen-Brightness-Control-through-Hand-Gesture

### Utilizes OS-specific brightness control libraries (win32api, win32con for Windows) to adjust screen brightness.

### Provides a more practical demonstration by actually adjusting screen brightness based on hand gestures.

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

## How the brightness can be increased or decreased?

The brightness of the display is controlled by mapping the distance between the thumb tip and index finger tip of the detected hand to a brightness value. The `map_hand_distance_to_brightness()` function scales the hand distance to a brightness value within a specified range. This brightness value is then used to adjust the display brightness using the `set_brightness()` function.

Here's a **breakdown of the brightness control process**:

**1.** Hand landmarks are detected using MediaPipe Hands.

**2.** The distance between the thumb tip and index finger tip is calculated.

**3.** This distance is mapped to a brightness value using the `map_hand_distance_to_brightness()` function. The distance is clamped between a minimum and maximum distance to ensure accurate mapping.

**4.** The resulting brightness value is applied to adjust the display brightness using the `set_brightness()` function.

**To increase or decrease the brightness**:

- Move the thumb tip closer to the index finger tip to decrease brightness.
- Move the thumb tip away from the index finger tip to increase brightness.

You can adjust the mapping parameters in the `map_hand_distance_to_brightness()` function to control the sensitivity and range of brightness adjustment based on your preference. Additionally, make sure that your system supports brightness adjustment through the `set_brightness()` function, as it relies on platform-specific methods.
