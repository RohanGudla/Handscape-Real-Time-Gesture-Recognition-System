# Hand Detection System

Hand Detection System utilizes the deep learning library from MediaPipe developed by Google for the task of hand detection and landmark localization. This system is capable of detecting hands in live video frames and performing detailed landmark localization, enabling the precise detection of key hand points.

## Input
- Live video frames

## Output
- Hand detected
  - Palm detection
  - 21-point detection

## Algorithm

### Palm Detection
To detect initial hand locations, the system employs a single-shot detector model that is optimized for real-time use on mobile devices. Detecting hands is a complex task, and this model is designed to work across various hand sizes with a large scale span, about 20 times relative to the image frame. It can also detect occluded and self-occluded hands.

![Palm Detection](https://user-images.githubusercontent.com/83566027/117607289-48794b80-b179-11eb-8e73-bdcb44870377.png)

### Hand Landmark Model
After palm detection across the entire image, the subsequent hand landmark model precisely localizes 21 3D hand-knuckle coordinates inside the detected hand regions through regression. This means the model directly predicts the coordinates of these keypoints. The model is trained to learn a consistent internal hand pose representation and remains robust even when dealing with partially visible hands and self-occlusions.

![Hand Landmark Model](https://user-images.githubusercontent.com/83566027/117607044-cb4dd680-b178-11eb-89f0-a7fbc3030105.png)

## Result
The system successfully detects and localizes hands in live video frames, allowing for real-time tracking of hand positions and movements.

![Result](https://user-images.githubusercontent.com/83566027/117607125-efa9b300-b178-11eb-843d-57e696f9e9c4.png)

## Output Video
You can watch a demonstration of the system's capabilities in the following video:

[Output Video](https://user-images.githubusercontent.com/83566027/117609051-e4f11d00-b17c-11eb-9e7c-4e3fa004b082.mp4)