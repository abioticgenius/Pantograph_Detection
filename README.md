# Pantograph Detection

This script processes a video to detect and analyze the movement of a pantograph, pantobar, and cables using YOLOv8 for object detection. It tracks horizontal and vertical movement, detects sparks, and records data in a CSV file.

## Requirements

- Python 3.6 or later
- OpenCV (`opencv-python`)
- NumPy
- `ultralytics` (for YOLOv8)

You can install the required packages using pip:

```bash
pip install opencv-python-headless numpy ultralytics
```
## Setup

- **YOLO Model**: Ensure you have a trained YOLOv8 model for object detection. Update the `model_path` variable with the path to your model's weights.

- **Video Paths**: Update `input_video_path` and `output_video_path` with the paths to your input and output video files, respectively.

- **CSV Output**: Set `csv_output_path` to the desired location for saving the CSV file that will contain movement and sparks data.

## Script Overview

- **Object Detection**: Uses YOLOv8 to detect pantograph, pantobar, and cables in each frame of the video.

- **Movement Tracking**: Calculates the horizontal and vertical movement of the pantograph between frames.

- **Sparks Detection**: Identifies sparks in the pantobar region by analyzing bright spots.

- **Contact Points**: Computes distances between the pantobar and cables at contact points.

- **CSV Logging**: Logs timestamped movement data and the number of sparks detected into a CSV file.

- **Video Output**: Saves the processed video with visual annotations.

## Usage

1. Update the `input_video_path`, `output_video_path`, and `csv_output_path` variables in the script with appropriate paths.

2. Run the script:

   ```bash
   python your_script_name.py
   ```
3. The script will process the input video, detect relevant objects, track movements, detect sparks, and save the results to the specified output video and CSV file.

## Example

```bash
import cv2
import numpy as np
import csv
from ultralytics import YOLO

# YOLO model path
model_path = '/path/to/your/yolo_model.pt'
model = YOLO(model_path)

# Video and CSV paths
input_video_path = '/path/to/input_video.mp4'
output_video_path = '/path/to/output_video.mp4'
csv_output_path = '/path/to/output_data.csv'

# Your script here
```
## Notes

- Ensure the YOLO model is correctly trained and configured for detecting the required objects.
- Adjust the detection parameters as needed for different video conditions.
- The output video and CSV file will be saved in the specified paths.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
