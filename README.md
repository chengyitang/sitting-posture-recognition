# Sit, Good boy! - Posture Detection System

A real-time sitting posture detection system that helps users maintain good posture while sitting. The system uses computer vision to analyze sitting posture and provides audio alerts when poor posture is detected.

## Demo

<video src="report/SitWell.mp4" controls></video>

## Overview

This system uses MediaPipe Pose and OpenCV to detect and analyze human posture in real-time through a webcam feed. When poor sitting posture is detected, the system plays an audio alert to remind the user to correct their posture.

## Key Features

- Real-time posture detection using webcam
- MediaPipe Pose landmark detection
- Neural network classification of posture (using AlexNet architecture)
- Audio alerts for poor posture detection
- Support for multiple deep learning models (AlexNet, VGG16, ResNet50)

## Technical Stack

- **OpenCV** - For video capture and image processing
- **MediaPipe** - For pose detection and landmark tracking
- **TensorFlow/Keras** - For deep learning model implementation
- **NumPy** - For numerical computations
- **Python** - Primary programming language

## How It Works

1. The system captures video feed from the webcam
2. MediaPipe Pose detects body landmarks in each frame
3. The landmarks are processed and fed into a trained neural network
4. The network classifies the posture as either correct or incorrect
5. If poor posture is detected for multiple consecutive frames, an audio alert is played

## Pose Detection Example

The system uses MediaPipe Pose to detect body landmarks:

| Original Image | Detected Landmarks |
|:-------------:|:-----------------:|
| ![Original sitting posture](dataset/raw/wrong/tang_wrong_31.png) | ![Detected pose landmarks](dataset/skeleton/wrong/xpose_242.png) |

The landmarks are extracted from the original image and used as input for the neural network classification.

## Model Comparison

Three different CNN architectures were evaluated:

| Model     | Accuracy | Layers | ILSVRC Year |
|-----------|----------|---------|-------------|
| AlexNet   | 92.22%   | 8       | 2012       |
| VGGNet16  | 97.78%   | 16      | 2014       |
| ResNet50  | 87.78%   | 50      | 2015       |

VGGNet16 achieved the highest accuracy of 97.78% and was selected as the final model for the system.
