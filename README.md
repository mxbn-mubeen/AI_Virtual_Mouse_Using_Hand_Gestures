# AI_Virtual_Mouse_Using_Hand_Gestures

Creating an AI-based virtual mouse using computer vision techniques is a great way to explore the intersection of software development and computer vision. Let's dive into the details of your project components:

1. **Hand Tracking Module (`handtrackingmodule.py`)**:
    - The `handDetector` class initializes the MediaPipe Hands module and sets parameters for hand detection and tracking confidence.
    - Key methods:
        - `findHands`: Converts the input image to RGB, processes it to find hand landmarks, and optionally draws the landmarks on the image.
        - `findPosition`: Extracts and returns the positions of hand landmarks along with a bounding box.
        - `fingersUp`: Determines which fingers are up based on landmark positions.
        - `findDistance`: Calculates the Euclidean distance between specified landmarks and visualizes it on the image.

2. **AI Virtual Mouse (`AI_Virtual_Mouse.py`)**:
    - Initialization:
        - Sets up the webcam and window dimensions.
        - Initializes the hand detector with a detection confidence threshold (0.60) and allows tracking of one hand at a time.
        - Retrieves the screen size using `pyautogui`.
    - Main Loop:
        - **Hand Landmarks Detection**:
            - Captures frames from the webcam and uses the hand detector to find hand landmarks.
        - **Finger Position and Status**:
            - Retrieves the positions of the index and middle finger tips.
            - Determines which fingers are up.
        - **Mouse Control**:
            - **Moving Mode**: If only the index finger is up, it maps the index finger position to screen coordinates, smoothens the movement, and moves the mouse cursor accordingly.
            - **Clicking Mode**: If both the index and middle fingers are up and close to each other, it simulates a mouse click.
        - **Frame Rate Display**:
            - Calculates and displays the frame rate on the screen to monitor performance.
        - **Display Frame**:
            - Shows the processed frame with hand landmarks and other visual aids.

3. **Code Summary**:
    - **Hand Tracking Module (`handtrackingmodule.py`)**:
        - Defines the `handDetector` class for hand detection and landmark processing using MediaPipe.
        - Provides methods for finding hand positions, determining finger status, and calculating distances between landmarks.
    - **AI Virtual Mouse (`AI_Virtual_Mouse.py`)**:
        - Utilizes the `handDetector` class for hand landmark detection.
        - Implements logic to control the mouse cursor and perform click actions based on hand gestures.
        - Displays the processed video feed with relevant visual aids.

**the steps for controlling the virtual mouse using hand gestures!:** 

1. **Package Installation**:
    - You've listed the necessary packages for your project. Here's a summary:
        - `opencv-contrib-python`: OpenCV library for computer vision tasks.
        - `numpy`: Essential for numerical operations and array manipulation.
        - `mediapipe`: Provides hand tracking capabilities.
        - `opencv-python-headless`: Headless version of OpenCV (without GUI support).
        - `pyautogui`: Allows simulating mouse and keyboard actions.
        - `opencv-python`: Another package for computer vision tasks.

2. **Mouse Control Steps**:
    - You've outlined the two main steps for controlling the virtual mouse:
        - **Step 1: Index Finger to Move the Cursor**:
            - Use the index finger to control the cursor's movement.
        - **Step 2: Joining Index and Middle Finger for Click Operations**:
            - When both the index and middle fingers are close together, simulate a mouse click.
