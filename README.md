# Webcam Object Detection with Haar Cascade Classifiers and Running in Google Co-lab

This Python code allows you to capture images from your webcam and detect specific objects using pre-trained Haar Cascade classifiers. The detected objects are surrounded by bounding boxes and labeled with text. The code is designed to run in a Jupyter Notebook or Google Colab environment, with some adjustments required for Google Colab.

## Motivating Article
S. Wattamwar, R. Mate, P. Rainchwar, S. Mantri and G. Sorate, "Optimal Face Recognition System using Haar Classifier," 2021 International Conference on Smart Generation Computing, Communication and Networking (SMART GENCON), Pune, India, 2021, pp. 1-7, doi: 10.1109/SMARTGENCON51891.2021.9645879. https://ieeexplore.ieee.org/abstract/document/9645879

## Related Work

colab-webcam https://github.com/theAIGuysCode/colab-webcam

Haarcascades https://github.com/opencv/opencv/tree/master/data/haarcascades

Google Colab: Access Webcam for Images and Video https://colab.research.google.com/drive/1QnC7lV7oVFk5OZCm75fqbLAfD9qBy9bw

Cascade Classification https://colab.research.google.com/github/computationalcore/introduction-to-opencv/blob/master/notebooks/4-Cascade_classification.ipynb

## Features

- Real-time video stream from the webcam
- Object detection using Haar Cascade classifiers
- Support for multiple object types: faces, smiles, and eyes
- Drawing of bounding boxes around detected objects
- Text labels on the bounding boxes indicating the object type
- Capture and save images with bounding boxes and labels
- Customizable file names based on the detected object type

## Results

### Captured Face
![](https://github.com/ericyoc/google_co-lab_haarcascade_capture_poc/blob/main/captured_face_with_menu.jpg)

### Captured Eyes
![](https://github.com/ericyoc/google_co-lab_haarcascade_capture_poc/blob/main/captured_eyes_with_menu.jpg)

### Captured Smile
![](https://github.com/ericyoc/google_co-lab_haarcascade_capture_poc/blob/main/captured_smile_with_menu.jpg)

## Prerequisites

- Python 3.x
- OpenCV (with pre-trained Haar Cascade classifiers)
- NumPy
- PIL (Python Imaging Library)
- IPython.display (for Jupyter Notebook or Google Colab)
- google.colab.output (for Google Colab)

## Running on Google Colab

To run this code on Google Colab, some adjustments are required:

1. Upload the necessary Haar Cascade classifier files (`haarcascade_frontalface_default.xml`, `haarcascade_smile.xml`, and `haarcascade_eye.xml`) to your Google Colab environment.
2. Import the required libraries from IPython.display and google.colab.output:

```python
from IPython.display import Image, Javascript, display
from google.colab.output import eval_js
```

3. Use the `eval_js` function from `google.colab.output` to execute the JavaScript code that captures the video stream and handles the user interface.
4. Use the `display` function from `IPython.display` to display the captured images in the Colab notebook.

## Usage

1. Run the Python script in a Jupyter Notebook or Google Colab environment.
2. A menu will prompt you to select the detection type:
   - `f`: Face detection
   - `s`: Smile detection
   - `e`: Eye detection
3. Enter your choice (e.g., `f` for face detection).
4. The webcam video stream will be displayed with bounding boxes and labels around the detected objects.
5. Click the "Capture Photo" button to capture the current video frame.
6. The captured image will be saved with a filename reflecting the selected detection type (e.g., `captured_face.jpg` for face detection).
7. The saved image will be displayed in the notebook or Colab environment.
8. After capturing the photo, the script will clean up the OpenCV resources and remove the preview window.

## Haar Cascade Classifiers

This code uses pre-trained Haar Cascade classifiers provided by OpenCV to detect specific objects in the video stream. These classifiers are machine learning models trained to recognize patterns and features associated with different object types.

The following Haar Cascade classifiers are supported:

- `haarcascade_frontalface_default.xml`: For detecting frontal faces
- `haarcascade_smile.xml`: For detecting smiles
- `haarcascade_eye.xml`: For detecting eyes

The code automatically loads the appropriate classifier based on the selected detection type and performs object detection on each video frame.

## Inference with Pre-trained Models

The Haar Cascade classifiers used in this code are pre-trained models provided by OpenCV. These models have been trained on large datasets of images to learn the visual patterns and features associated with specific object types, such as faces, smiles, and eyes.

When the code runs, it loads the pre-trained Haar Cascade classifier model and uses the `detectMultiScale` function from OpenCV to perform object detection on the video frames. The function returns the coordinates of the bounding boxes where the objects are detected.

The code then draws the bounding boxes and labels on the video frames and the captured images, allowing you to visualize the detected objects.

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

##Disclaimer 
This repository is intended for educational and research purposes.
