# Dino-Game-With-Hand-Gesture
Title: Google Dino Game With Hand Gestures


Abstract: In this project, we use OpenCV and background subtraction technique to isolate the hand image from the background through segmentation. By using hand gestures, we control the movement of a game character, such as making it jump or duck, based on the number of fingers we show to the camera.

Introduction:
Gesture recognition is becoming a popular research area due to its broad range of applications, including gaming, robotics, and sign language recognition. In this project, we focus on developing a simple game using hand gestures to control the game character's movements. We use OpenCV, a popular computer vision library, to capture the video frames, detect and isolate the hand from the background, and recognize the hand gestures to control the game character.

Problem Statement:
The problem we aim to solve is to develop a simple game using hand gestures for controlling the game character's movements. We want to use computer vision techniques to detect and isolate the hand region from the background and recognize the hand gestures to control the game character.

Methodology or Approach:
To solve this problem, we first let the computer save the background on which we will demonstrate the game using hand gestures. We show the computer the background and let it save the background to memory by letting it take the running average of the background for 30 frames. After 30 frames have passed, the background has been saved. Now we introduce our hand into the camera, and once the camera sees the hand in front of the background, the frame is read and stored. This frame is subtracted from the stored background, and the absolute of this subtraction matrix is taken to obtain the hand region. After thresholding, we find the contour having the maximum area, assuming that our hand region will have the maximum area in the camera region of interest. Using the cv2 convex hull function, we are able to get the extreme points of the hand on camera. By finding the mean of opposite laying coordinates, we can find the center of the palm. We construct a circle around the center of the palm and see where the circle and fingers intersect. The number of times the circle interests with the fingers will be the number of fingers open, which we use to control the game character's movements.
