# YOLOv9 + DeepSORT: Real-Time Object Detection and Tracking

This project combines **YOLOv9** for object detection and **DeepSORT** for object tracking, creating a powerful tool for real-time video analytics and multi-object tracking. The integrated system can detect and track multiple objects across video frames, supporting various applications such as surveillance, traffic monitoring, and automated inspection.

## Project Overview

### What is This Project?

This project brings together two advanced algorithms:
- **YOLOv9** (You Only Look Once): A state-of-the-art, real-time object detection algorithm that provides high accuracy and speed, capable of detecting multiple object classes in a single forward pass.
- **DeepSORT** (Simple Online and Realtime Tracking with a Deep Association Metric): A multi-object tracking algorithm that associates detected objects across frames using motion and appearance cues, making it robust for real-world applications.

### Key Features

- **Real-Time Detection and Tracking**: Capable of handling high FPS video streams.
- **Multi-Object Tracking**: Tracks multiple object instances, assigning unique IDs for each instance.
- **Flexibility**: Supports various configurations for single, dual, and triple tracking setups, adaptable to different use cases.
- **Benchmarking and Performance Evaluation**: Includes scripts to benchmark the model and assess accuracy and runtime performance.

## Technologies Used

- **Languages**: Python
- **Deep Learning Framework**: PyTorch
- **Computer Vision**: OpenCV
- **Object Detection**: YOLOv9
- **Object Tracking**: DeepSORT
- **GPU Acceleration**: CUDA (optional)
- **Dependencies Management**: Pip (via `requirements.txt`)
- **Version Control**: Git

## How It Works

1. **Detection with YOLOv9**:
   YOLOv9 detects objects in each frame of a video, classifying them into predefined classes. This model outputs bounding boxes and class scores for each detected object.

2. **Tracking with DeepSORT**:
   After detection, DeepSORT assigns each detected object a unique ID, allowing consistent tracking across frames. DeepSORT uses a combination of motion information (via Kalman filtering) and appearance features (via a deep learning-based association metric) to maintain accurate tracking.

3. **Data Flow**:
   - Each frame is processed by YOLOv9 to detect objects.
   - The detections are passed to DeepSORT, which associates them with previously tracked objects based on similarity metrics.
   - The final output is a video or sequence with each object consistently labeled across frames.

## Problem It Solves

This integrated system addresses several real-world challenges:
- **Real-Time Multi-Object Tracking**: Ideal for applications that require instant feedback, such as live surveillance, autonomous vehicles, and event monitoring.
- **Reduced Complexity in Data Analysis**: Provides structured data on object trajectories, which can be used for further analysis, like calculating movement patterns, density, and duration.
- **Scalability**: Supports multiple objects and can adapt to various scenarios by simply adjusting detection classes or model configurations.

## Getting Started

### Prerequisites

- **Python 3.10+**
- **CUDA** (for GPU acceleration, optional but recommended)
- Other dependencies are listed in `requirements.txt`.

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/username/YOLOv9-DeepSORT-Object-Tracking.git
   cd YOLOv9-DeepSORT-Object-Tracking
2. Install Dependecies:
   ```bash
   git install -r requirements.txt

### Usage
1. Single Camera Detection and Tracking:
   ```bash
   python detect.py --source your_video.mp4 --output results/
2. Dual Camera Detection and Tracking:
   ```bash
   python detect_dual.py --source video1.mp4 video2.mp4 --output results/
3. Triple Camera Detection and Tracking:
   ```bash
   python detect_triple.py --source video1.mp4 video2.mp4 video3.mp4 --output results/

### Training
- **To Train YOLO on Custom Data**
   ```bash
   python train.py --data data.yaml --cfg yolov9.yaml --weights yolov9.pt

### Benchmarks and Evaluation
- **To evaluate Model's Performance**
  ```bash
  python benchmarks.py --source your_test_dataset/

## Folder Structure

- **classify/**: Scripts for image classification tasks.
- **detect.py, detect_dual.py, detect_triple.py**: Main scripts for detection and tracking with single, dual, and triple cameras.
- **train.py, train_dual.py, train_triple.py**: Training scripts for single, dual, and triple models.
- **val.py, val_dual.py, val_triple.py**: Validation scripts.
- **benchmarks.py**: Script to benchmark model performance.
- **requirements.txt**: Lists required packages.

## Example Outputs

The system outputs video files with tracked objects labeled and annotated across frames. Each object is assigned a unique ID, making it easy to follow their movement over time.

## Resources and Further Reading

- **YOLOv9 Paper**: [Read YOLOv9](https://arxiv.org/pdf/1706.03762.pdf)
- **DeepSORT Paper**: [Read DeepSORT](https://arxiv.org/pdf/1703.07402.pdf)
- **Object Tracking Overview**: [Tracking in Computer Vision](https://www.cs.cmu.edu/~kkitani/pdf/kitani/kitani_iccv13.pdf)

  
   


