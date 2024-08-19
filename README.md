# Pantograph_Detection

This repository contains a Python-based application designed to detect and analyze interactions between a pantograph and overhead cables in railway systems. The project uses a YOLOv8 object detection model to identify key components such as the pantograph, pantobar, and cables in a video feed. The application also tracks the movements of the pantograph and detects sparks that may occur during its interaction with the cables.

## Features

- **Object Detection**: Uses a YOLOv8 model to detect pantographs, pantobars, and cables in video frames.
- **Spark Detection**: Identifies sparks occurring within the pantograph box using image processing techniques.
- **Movement Tracking**: Tracks horizontal and vertical movements of the pantograph across video frames.
- **Contact Points Calculation**: Detects and calculates the distances between the pantobar and cables.
- **Video Annotation**: Annotates the video with detected objects, movements, contact points, and spark detection information.
- **CSV Logging**: Records movement data and spark detection status at each second of the video.

## Prerequisites

To run this project, you need to have the following installed:

- Python 3.7 or later
- OpenCV
- NumPy
- Ultralytics YOLOv8

You can install the required Python packages using pip:

```bash
pip install opencv-python-headless numpy ultralytics
```

## Getting Started

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/yourusername/pantograph-detection.git
   cd pantograph-detection
   ```

2. **Prepare the YOLOv8 Model:**

   - Place the trained YOLOv8 model (`best.pt`) in the project directory. Ensure the model is trained to detect the pantograph, pantobar, and cables.

3. **Provide Input Video:**

   - Place your input video in the project directory or provide the path to the video file in the script.

4. **Run the Script:**

   Execute the main script to process the video:

   ```bash
   python detect_pantograph.py
   ```

   Replace `detect_pantograph.py` with the filename you’ve given to the script.

## Detailed Workflow

1. **Video Input**: The script reads the input video frame by frame.

2. **Object Detection**: The YOLOv8 model detects objects (pantograph, pantobar, and cables) in each frame.

3. **Spark Detection**: The script processes each frame to detect any sparks within the pantograph bounding box.

4. **Movement Calculation**: It tracks the center position of the pantograph across frames to calculate horizontal and vertical movements.

5. **Contact Points**: The script calculates the contact points between the pantobar and cables, measuring the distance between the pantobar’s center and each contact point.

6. **Video Annotation**: All detections, movements, and spark events are annotated on the video.

7. **Data Logging**: Movements and spark detection statuses are logged into a CSV file with timestamps.

## Output

- **Annotated Video**: The processed video with annotations is saved as `output.mp4` (or any specified name).
- **CSV Log**: A CSV file (`movement_data.csv`) is generated, logging the following for each second:
  - Timestamp (in seconds)
  - Horizontal Movement (in pixels)
  - Vertical Movement (in pixels)
  - Spark Detected (Boolean)

## Example Usage

Here's an example of how to execute the script:

```bash
python detect_pantograph.py --model-path path/to/best.pt --input-video path/to/input.mp4 --output-video path/to/output.mp4 --csv-output path/to/movement_data.csv
```

## Future Enhancements

- **Real-time Processing**: Implement real-time video processing and detection.
- **Advanced Spark Detection**: Enhance spark detection using more sophisticated image processing techniques or deep learning models.
- **UI Integration**: Develop a user interface for easier interaction with the tool.
- **Model Improvements**: Fine-tune the YOLOv8 model for higher accuracy in detection.

## Contributing

Contributions are welcome! If you have any ideas, suggestions, or issues, please feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- **Ultralytics YOLO**: Thanks to the Ultralytics team for developing and maintaining the YOLOv8 model.
- **OpenCV**: For providing a robust computer vision library.

## Contact

For any questions or inquiries, please contact [proshan2004@gmail.com].


