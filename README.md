# Face Detection on Images Using MATLAB

This project demonstrates a simple implementation of **face detection** using MATLAB's `vision.CascadeObjectDetector`. The program reads an image, resizes it if necessary, and detects the face within the image. The detected face is then highlighted with a bounding box and displayed.

## Features

- **Face Detection**: Automatically detects faces in a given image.
- **Image Resizing**: Resizes the image if its width exceeds a preset size to ensure efficient face detection.
- **Face Highlighting**: Draws a bounding rectangle around the detected face.
- **Image Display**: Displays the processed image with the detected face highlighted.

## How It Works

1. **Image Input**: The program reads an input image (`1.jpg`) using the `imread` function.
2. **Resizing**: If the width of the image exceeds 320 pixels, it resizes the image while maintaining the aspect ratio.
3. **Face Detection**: The `vision.CascadeObjectDetector` is used to detect the face in the image. The coordinates of the detected face are stored.
4. **Highlighting the Face**: A rectangle is drawn around the detected face using the `insertShape` function.
5. **Display**: The resulting image with the face highlighted is displayed using `imshow`.

## Project Structure

- **Image Input**: The image file `1.jpg` is used as input to detect faces.
- **MATLAB Functions**:
  - `imread`: Reads the image from a file.
  - `imresize`: Resizes the image while maintaining the aspect ratio.
  - `vision.CascadeObjectDetector`: Detects faces using the Viola-Jones algorithm.
  - `insertShape`: Draws shapes (in this case, a rectangle) on the image.
  - `imshow`: Displays the processed image.

## Prerequisites

- **MATLAB**: Make sure you have MATLAB installed.
- **Computer Vision Toolbox**: The `vision.CascadeObjectDetector` is part of the Computer Vision Toolbox, which must be installed.

## Installation and Setup

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/yourusername/face-detection-matlab.git
    cd face-detection-matlab
    ```

2. **Ensure MATLAB is Installed**: Ensure you have MATLAB with the **Computer Vision Toolbox**.

3. **Prepare Your Image**: Place the image (`1.jpg`) in the working directory.

4. **Run the MATLAB Script**:
    Open MATLAB, navigate to the project folder, and run the script:
    ```matlab
    face_detection_script
    ```

## Example Output

When the script runs, the output will display the image with the detected face highlighted by a rectangle, and the title "Detected face" will be shown in the figure window.

## Customization

You can customize the image size or detector options:

- **Image Width**: Modify the resizing threshold:
  ```matlab
  if width > 320
      the_Image = imresize(the_Image, [320 NaN]);  % Change 320 to another value
  end


## Code

```matlab
the_Image = imread('1.jpg');
[width, height] = size(the_Image);

if width > 320
    the_Image = imresize(the_Image, [320 NaN]);
end

face_Detector = vision.CascadeObjectDetector();

location_of_the_Face = step(face_Detector, the_Image);

detected_Image = insertShape(the_Image, 'rectangle', location_of_the_Face);

figure;
imshow(detected_Image);
title('Detected face')


