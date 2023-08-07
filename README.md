# orbslam2
# ORB-SLAM 2 Installation Guide
This post is about how to build and run ORB SLAM2. If you follow the following guidance in the orders, you will not face any troubles with ORB SLAM2 installation. You can easily run ORB SLAM2 in here, then you can install it in your local to modify or do other things.

# 1. OS
For now, we have checked for two OS as followed. If you are trying to use other OS, please refer the official documents or other guidance.

- Ubuntu(Debian, Linux)
- SL2

# 2. Prerequisites
## 2.1. Kitti Dataset Download

**NOTE:Dataset requires about 22GB that means it requires much time to download, so it would be better to download first and then move to the next step.**
First, you can follow the link as followed. Then, you can download the dataset via [Download odometry data set (grayscale, 22 GB)](https://www.cvlibs.net/datasets/kitti/user_login.php)

[The KITTI Vision Benchmark Suite](https://www.cvlibs.net/datasets/kitti/user_login.php)

 **You need to sign up before downloading.**

## 2.2. Update Package Info

`sudo apt update && sudo apt upgrade`

## 2.3. OpenCV

Reference: [How to install OpenCV on Ubuntu 18.04](https://linuxize.com/post/how-to-install-opencv-on-ubuntu-18-04/)


### 2.3.1. Install Dependency
 **You need to change the last libdc1394-22-dev into libdc1394-dev if you are using Ubuntu 22.04 or upper version.**

 `sudo apt install build-essential cmake git pkg-config libgtk-3-dev \
 libavcodec-dev libavformat-dev libswscale-dev libv4l-dev \
 libxvidcore-dev libx264-dev libjpeg-dev libpng-dev libtiff-dev \
 gfortran openexr libatlas-base-dev python3-dev python3-numpy \
 libtbb2 libtbb-dev libdc1394-22-dev`
 ### 2.3.2. Download OpenCV, OpenCV_contrib repository

 `git clone https://github.com/opencv/opencv.git`
 
 `git clone https://github.com/opencv/opencv_contrib.git`

### 2.3.3. OpenCV, OpenCV_contrib 3.4.9 branch checkout

**Note that OpenCV 4.x version is not compatible with ORB SLAM2. Please keep in mind that OpenCV 4.x will be set if you install with default option.**

`cd opencv`

`/opencv$ git checkout 3.4.9`

`/opencv$ cd ../opencv_contrib`

`/opencv_contrib$ git checkout 3.4.9`

### 2.3.4. CMake
`/opencv_contrib$ cd ../opencv`

`/opencv$ mkdir build && cd build`

`/opencv/build$ cmake -D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules ..`

### 2.3.5. Build OpenCV
`/opencv/build$ make -j8`

### 2.3.6. Install OpenCV
`/opencv/build$ sudo make install`

## 2.4 Eigen3
`sudo apt install libeigen3-dev`

## 2.5. Pangolin
[Reference1: https://blog.csdn.net/Robert_Q/article/details/121690089]()
[]()

### 2.5.1. Download Pangolin repository
`git clone --recursive https://github.com/stevenlovegrove/Pangolin.git`

`cd Pangolin`

### 2.5.2. Install Dependency
`/Pangolin$ ./scripts/install_prerequisites.sh recommended`

### 2.5.3. Pangolin v0.5 branch checkout
**Note that ORB SLAM2 is not compatible with Pangolin v0.6 or upper version. Please keep in mind that Pangolin v0.8 will be installed if you install with default option.**
`/Pangolin$ git checkout v0.5`

### 2.5.4. Modify Pangolin source code

### 2.5.5. Build Pangolin
`/Pangolin$ cmake -B build`
`/Pangolin$ cmake --build build`

### 2.5.6. Install Pangolin
`/Pangolin$ cd build`

`/Pangolin/build$ sudo make install`

# 3. ORB SLAM 2
## 3.1. Download ORB-SLAM 2 repository
`git clone https://github.com/raulmur/ORB_SLAM2.git ORB_SLAM2`

## 3.2. Modify ORB-SLAM 2 source code

## 3.3. Build ORB-SLAM 2
`cd ORB_SLAM2`

`/ORB_SLAM2$ ./build.sh`

# 4. Xming(Optional for WSL2 environment)

# 5. Run ORB-SLAM 2
`/ORB_SLAM2$ ./Examples/Monocular/mono_kitti Vocabulary/ORBvoc.txt Examples/Monocular/KITTI00-02.yaml [kitti dataset 경로]/odometry_gray/sequences/00`


 
