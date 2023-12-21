# Yolo-Object-Detection-With-Intel-Realsense-Camera
The algorithm does not change the YoloV5 source code, but creates a new python file: pyrealsense2_camera.py.

## Install
### 1.Install cuda
URL：https://developer.nvidia.com/cuda-toolkit

### 2.Create YoloV5 environment && install requirements
> conda create --name yolov5 python=3.10

> conda activate yolov5

> install pytorch URL：https://pytorch.org/  

> git clone https://github.com/Jumbo-zczlbj0/YoloV5_D415.git

> cd YoloV5_D415 

> pip install -r requirements.txt 

### 3.Install Intel RealSense SDK 2.0

> Choose the version that suits you based on your computer system and install SDK-2：https://www.intelrealsense.com/sdk-2/

> Install pyrealsense2：pip install pyrealsense2

### 4.Install other package
Sound module, used to play the name, confidence, and depth of the detected object 

> pip install pyttsx3

Multithreading module for parallel sound module and detection module
> pip install threading

## Try
Download and change the weight file path.(Weight link: https://github.com/ultralytics/yolov5)

> python pyrealsense2_camera.py

## Train YOLO V5
Log in to the roboflow website and label your own dataset. Select YOLOV5 format to download and replace the .yaml file path in the code.(The yaml generated by the website contains the train and val paths, please replace them with your own paths) 
The official connection of yoloV5 has detailed tutorials and You can also use other label methods, such as labelme. Tutorials URL: https://docs.ultralytics.com/integrations/roboflow/?h=roboflow#upload-convert-and-label-data-for-yolov8-format

> python train.py --img 640 --batch 64 --epochs 300 --data coco128.yaml --weights yolov5s.pt --cache

# Running YOLOV5 using Realsense Camera on Jetson Nano Developer Kit

## InstallA Jetson Nano - Ubuntu 20.04 image with OpenCV, TensorFlow and Pytorch


Tutorials URL: https://github.com/Qengineering/Jetson-Nano-Ubuntu-20-image

BalenaEtcher: https://etcher.balena.io/#download-etcher


1.Get a 32 GB (minimal) SD card with exFat to hold the image.

2.Download the image JetsonNanoUb20_3b.img.xz (8.7 GByte!) from our Sync.

3.Flash the image on the SD card with the Imager or balenaEtcher.

4.nsert the SD card in your Jetson Nano and enjoy.

Password: jetson

（The above content comes from Qengineering： https://github.com/Qengineering/Jetson-Nano-Ubuntu-20-image）

## Install
### 1.Install exfat
> sudo apt-get install exfat-fuse exfat-utils

### 2.Install pip
> Download: https://bootstrap.pypa.io/get-pip.py 

> cd Downloads

> python3 get-pip.py

### 3.Install SDK 2.0
Tutorials URL: https://github.com/IntelRealSense/librealsense/blob/master/doc/installation_jetson.md

### 4.Install environment
> git clone https://github.com/Jumbo-zczlbj0/YoloV5_D415.git

> cd YoloV5_D415 

requirements_Jetson.txt add pyrealsense2 && pyttsx3

> pip3 install -r requirements_Jetson.txt 

### 5.Install espeak
> sudo apt-get install espeak

## Run
> python3 pyrealsense2_camera.py
