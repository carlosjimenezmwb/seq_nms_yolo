# Seq_nms_YOLO

#### Membres: Yunyun SUN, Yutong YAN, Sixiang XU, Heng ZHANG

---

## Introduction

![](img/index.jpg) 

This project combines **YOLOv2**([reference](https://arxiv.org/abs/1506.02640)) and **seq-nms**([reference](https://arxiv.org/abs/1602.08465)) to realise **real time video detection**.

[Tutorial in Ubuntu]
## Steps
1. Open a terminal.
2. Create a virtual environment with python 2.7:
   - `conda create --name EnvExample python=2.7`
   - `conda activate EnvExample`
3. Clone the repository:
   - `git clone https://github.com/carlosjimenezmwb/seq_nms_yolo.git`
4. Make the project:
   - `cd seq_nms_yolo`
   - `make`
5. Download the yolo.weights and tiny-yolo.weights:
   - `wget https://pjreddie.com/media/files/yolo.weights`
   - `wget https://pjreddie.com/media/files/yolov2-tiny.weights`
6. Make sure you have the following libraries installed (with indicated versions):
   - cv2: `pip install opencv-python==4.2.0.32`
   - matplotlib: `pip install matplotlib`
   - scipy: `pip install scipy`
   - pillow: `conda install -c anaconda pillow`
   - tensorflow: `conda install tensorflow=1.15`
   - tf_object_detection: `conda install -c conda-forge tf_object_detection`
7. Copy a video file to the video (/seq_nms_yolo/video) folder, for example, 'input.mp4';
8. Go to the directory /seq_nms_yolo/video and run video2img.py and get_pkllist.py:
   - `python video2img.py -i input.mp4`
   - `python get_pkllist.py`
9. Export the paths:
   - `export PATH=/usr/local/cuda-10.1/bin${PATH:+:${PATH}}`
   - `export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-10.1/lib64`
   - `export LIBRARY_PATH=$LIBRARY_PATH:/usr/local/cuda-10.1/lib64`
10. Return to root folder and run `yolo_seqnms.py` to generate output images in `video/output`:
    - `python yolo_seqnms.py`
11. If you want to reconstruct a video from these output images, you can go to the video folder and run `img2video.py`:
    - `python img2video.py -i output`

And you will see detection results in `video/output`

## Reference

This project copies lots of code from [darknet](https://github.com/pjreddie/darknet) , [Seq-NMS](https://github.com/lrghust/Seq-NMS) and  [models](https://github.com/tensorflow/models).

Main reference: https://github.com/melodiepupu/seq_nms_yolo. The purpose of this project was to create easy-to-understand instructions to facilitate accessibility.
