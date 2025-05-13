# University-Vehicle-Tracker

An integrated system for vehicle tracking and identification on university campuses. This system combines license plate recognition and facial recognition to identify vehicles and their occupants in real-time for Automated Attendance Tracking.

## Features

- **License Plate Detection**: Detects both rectangular and square license plates
- **License Plate Recognition (LPR)**: Extracts and recognizes characters from license plates
- **Face Detection**: Locates faces in video frames
- **Face Recognition**: Identifies known individuals from detected faces
- **Real-time Processing**: Processes video stream with FPS counter

## Project Structure

```
University-Vehicle-Tracker/
├── Character-Time-series-Matching/  # License plate recognition components
│   ├── Char_detection_yolo.py       # Character detection using YOLOv5
│   ├── process_plate.py             # License plate processing
│   ├── evaluate.py                  # Evaluation script
│   └── character_name.txt           # Character classes
├── face-recognition/                # Face recognition components
│   ├── detect.py                    # Face detection module
│   ├── recognize.py                 # Face recognition module
│   ├── main.py                      # Main face recognition application
│   └── insightface/                 # Face embedding model
├── detection.py                     # Main application script
├── requirements.txt                 # Project dependencies
└── README.md                        # Project documentation
```

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/University-Vehicle-Tracker.git
cd University-Vehicle-Tracker
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Download required model weights:
   - Character detection models: `object.pt` and `char.pt` (place in `Character-Time-series-Matching/Vietnamese/`)
   - Face detection model: `yolov5n-0.5.pt` (place in `face-recognition/yolov5_face/`)
   - Face recognition model: `resnet100_backbone.pth` (place in `face-recognition/insightface/`)

## Usage

Run the main detection script:
```bash
python detection.py
```

The system will:
1. Access your webcam
2. Detect and recognize license plates
3. Detect and recognize faces
4. Display results in real-time with bounding boxes and labels

To exit the application, press 'q'.

## Dependencies

- PyTorch
- OpenCV
- NumPy
- SQLAlchemy
- TorchVision
- YOLOv5 (included)
- InsightFace (included)

## Model Information

- **License Plate Detection**: YOLOv5 model trained on license plate data
- **Character Recognition**: YOLOv5 model trained on license plate characters
- **Face Detection**: YOLOv5-face model (`yolov5n-0.5.pt`)
- **Face Recognition**: iresnet100 backbone for face embedding

## License

Refer to the LICENSE file for licensing information.


## TODOS
1. Increase FPS
2. Improve character mapping on indian license plates
3. Store recognized input in sqlite database
4. Add Jetson Nano support
