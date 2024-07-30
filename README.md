# real-time-object-detection


https://github.com/user-attachments/assets/8d742918-f65b-45c6-b4df-6f821ecfc5be



## Table of Contents
1. [Installation Instructions](#installation-instructions)
   - [Prerequisites](#prerequisites)
   - [Dependencies](#dependencies)
2. [Usage](#usage)
   - [Running the Application](#running-the-application)
   - [Example](#example)
3. [Features](#features)
4. [Configuration](#configuration)

## Installation Instructions

### Prerequisites
Before you begin, ensure you have met the following requirements:
- You have installed Python 3.6 or later.
- You have a working installation of Jupyter Notebook.
- You have `pip` installed.

### Dependencies
This project uses the following libraries and packages:

- argparse
- os
- matplotlib
- scipy
- numpy
- pandas
- PIL
- tensorflow
- yad2k

You can install the required packages using the following command:
```sh
pip install argparse os matplotlib scipy numpy pandas pillow tensorflow git+https://github.com/allanzelener/YAD2K.git
```

## Usage

### Running the Application
To use this project, follow these steps:

1. **Clone the repository**:
    ```sh
    git clone <repository_url>
    cd <repository_directory>
    ```

2. **Launch Jupyter Notebook**:
    ```sh
    jupyter notebook
    ```

3. Open the notebook file `Autonomous_driving_application_Car_detection.ipynb` and run the cells sequentially.

### Example
The application processes images to detect cars. Here is an example of how to use the provided functions:

1. **Load and preprocess an image**:
    ```python
    image, image_data = preprocess_image("path_to_image", model_image_size=(608, 608))
    ```

2. **Load the YOLO model**:
    ```python
    yolo_model = load_model("model_data/yolo.h5")
    ```

3. **Run the model and get the output**:
    ```python
    yolo_outputs = yolo_head(yolo_model.output, anchors, len(class_names))
    ```

4. **Filter boxes**:
    ```python
    scores, boxes, classes = yolo_eval(yolo_outputs, image_shape)
    ```

5. **Draw bounding boxes**:
    ```python
    draw_boxes(image, boxes, classes, class_names, scores)
    ```

## Features
- **YOLO Model Integration**: Utilizes the YOLO (You Only Look Once) model for object detection.
- **Image Preprocessing**: Supports image preprocessing including resizing and normalization.
- **Bounding Box Visualization**: Visualizes detected objects with bounding boxes.
- **Confidence Thresholding**: Filters detections based on confidence scores.

## Configuration
Configuration details for the YOLO model and detection parameters are as follows:

- **YOLO Configuration Files**: The project uses pre-trained weights and configuration files available from the YAD2K repository.
- **Non-Max Suppression Threshold Settings**: Modify the class score threshold as needed. For example:
    ```python
    threshold = 0.6
    ```
