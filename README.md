
## Installation


```bash
This repository provides a demo script for performing object detection on video files using the MMDetection framework. The script allows you to specify a video file, configuration file, and a checkpoint file to detect objects in the video frames and optionally save the output to a new video file or display it in a window.

## Installation

To use this script, you need to install MMDetection and its dependencies. Follow these steps to set up the environment:

```
1. **Clone the repository:**

```bash
   git clone https://github.com/open-mmlab/mmdetection.git
   cd mmdetection
```
2. **Install required packages:**
```bash
pip install -r requirements/build.txt
pip install -v -e .  # install the package in editable mode
```
3. **Install additional dependencies for video processing:**

```bash
pip install opencv-python
```
4. **Set up MMDetection for GPU support (if applicable):**\
Ensure that you have installed the correct version of [PyTorch](https://pytorch.org/get-started/previous-versions/) for your system.

## Usage

To run the video demo, use the following command in your terminal. Make sure to provide paths to your video file, config file, and checkpoint file.

```python
python video_demo.py --video <VIDEO_FILE> --config <CONFIG_FILE> --checkpoint <CHECKPOINT_FILE> --out <OUTPUT_FILE>
```
```bash
Arguments
--video: Path to the input video file. Default is demo.mp4.
--config: Path to the model configuration file. Default is configs/rtmdet_l_8xb32-300e_coco.py.
--checkpoint: Path to the pre-trained model checkpoint. Default is checkpoints/rtmdet_l_8xb32-300e_coco_20220719_112030-5a0be7c4.pth.
--device: Device used for inference (e.g., cuda:0 or cpu). Default is cuda:0.
--score-thr: Bounding box score threshold for detections. Default is 0.3.
--out: Path to the output video file. Default is ./output/video_demo.mp4.
--show: Show video during processing.
--wait-time: The interval of show (s), 0 is block. Default is 1.
```

## Contributing

Configuration
You can modify the configuration files to adjust parameters such as input size, number of classes, and model architecture. The configuration files can be found in the configs/ directory.

Example Configuration Changes
Change the number of classes in the config file by updating num_classes in the model section.
Adjust the input size by changing input_size in the data section.\


## Example Command
```bash
python video_demo.py --video input_video.mp4 --config configs/rtmdet_l_8xb32-300e_coco.py --checkpoint checkpoints/rtmdet_l_8xb32-300e_coco_20220719_112030-5a0be7c4.pth --out output_video.mp4 --show
```

This command processes the input_video.mp4, runs the detection using the specified configuration and checkpoint, and outputs the results to output_video.mp4, while also displaying the video in a window.
## Requirements

Python 3.x\
MMDetection \
OpenCV \
PyTorch\
For additional package requirements, refer to the requirements/build.txt file.
