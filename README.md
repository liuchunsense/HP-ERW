# **HP-ERW**
## **Driver Gaze Zone Estimation via Head Pose Fusion Assisted Supervision and Eye Region Weighted Encoding**
## What is HP-ERW?
Driver gaze zone estimation is an important task in Advanced Driver Assistance Systems (ADAS), which suffers difficulties including head pose, capture direction, glass occlusion, and real-time requirement, etc. Most previous methods combine face modalities and head pose using an easy concat process, which may result in over-fitting due to the unbalanced dimension of the face and head pose. To address the gaze zone estimation problem, we propose a novel driver gaze zone estimation structure named Head Pose Fusion Assisted supervision & Eye Region Weighted Encoding (HP-ERW).  This structure can improve the gaze estimation task accuracy and achieve 23.5 fps real-time application in driver monitoring.

### 1 Datasets
#### DWG
[DWG](https://arxiv.org/abs/2004.05973) dataset was collected during different times of day. 9 gaze zones were selected from rearview mirror, side mirrors, radio, speedometer and windshield. DWG dataset contains 338 subjects (247 male and 91 females). It contains 29,392 frames of 286 subjects for training and contains 9,995 frames of 52 subjects for testing.

#### Lisat Gaze Data
[Lisat Gaze Data](https://github.com/arangesh/GPCycleGAN) is a dataset collected for intelligent and safe automobiles at the University of California. In this study, we use Lisat Gaze Data V0 (introduced in [On Generalizing Driver Gaze Zone Estimation using Convolutional Neural Networks](http://cvrr.ucsd.edu/publications/2017/IV2017-VoraTrivedi-OnGeneralizingGazeZone.pdf)) and Lisat Gaze Data V1 (introduced in [Driver Gaze Zone Estimation Using Convolutional Neural Networks: A General Framework and
Ablative Analysis](http://cvrr.ucsd.edu/publications/2018/sourabh_gaze_zone.pdf)). The training set in the V0 dataset contains 24,622 half-face images and the test set contains 4,268 half-face images; The training set in the V1 dataset contains 25,183 half-face images and the test set contains 4,822 half-face images. The datasets collects images with 7
gaze zones including front windshield, right side, left side, center console (infotainment panel), center rearview mirror, speedometer and the "closed eye" state when the driver blinks.

### 2 Modified tools in our pipeline
#### Driver location area estimation
#### Face detector
The [Dockerface](https://github.com/natanielruiz/dockerface) is used to detect the driver face.
#### Face landmarks detector
This study adopts [2D-FAN](https://github.com/tanmaysingha/2D-3D-FAN) trained on the LS3D-W dataset in our pipeline.
#### Head pose detector
we use the solvePnP function in the OpenCV library to output rotation matrix R and translation matrix T. And we convert these matrices to Euler angle output as driver’s head pose.
### 3 Experimental results












## Terms and Conditions of Use

### 1. Privacy

This dataset is made available for academic use only. If you find your vehicle or personal information in this dataset, please contact us and we will remove the corresponding information from our dataset. We are not responsible for any actual or potential harm as the result of using this dataset.

### 2. Copyright

The copyright of the UVSD dataset is reserved by the Lab of computer vision and pattern recognition, Shandong University, China. The dataset described on this page is distributed under the Creative Commons Attribution-NonCommercial-ShareAlike 3.0 License, which implies that you must: 
(1) Attribute the work as specified by the original authors;
(2) May not use this work for commercial purposes;
(3) If you alter, transform, or build upon this work, you may distribute the resulting work only under the same license. 
The dataset is provided "as it is" and we are not responsible for any subsequence from using this dataset.
