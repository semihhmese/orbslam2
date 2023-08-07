# orbslam2
ORB-SLAM 2 Installation GuidePermalink
This post is about how to build and run ORB SLAM2. If you follow the following guidance in the orders, you will not face any troubles with ORB SLAM2 installation. Special thanks to HeejoonLee, our team provide Docker images for easy way in our blog. You can easily run ORB SLAM2 in here, then you can install it in your local to modify or do other things.

# 1. OS
For now, we have checked for two OS as followed. If you are trying to use other OS, please refer the official documents or other guidance.

- Ubuntu(Debian, Linux)
- SL2

# 2. Prerequisites
## 2.1. Kitti Dataset Download
**NOTE:Dataset requires about 22GB that means it requires much time to download, so it would be better to download first and then move to the next step.
https://www.cvlibs.net/datasets/kitti/user_login.php
You need to sign up before downloading.

## 2.2. Update Package Info
~$ sudo apt update && sudo apt upgrade

## 2.3. OpenCV

Reference: How to install OpenCV on Ubuntu 18.04
https://linuxize.com/post/how-to-install-opencv-on-ubuntu-18-04/

https://itslinuxfoss.com/guide-install-opencv-ubuntu/

## 2.3.1. Install Dependency
💡 You need to change the last libdc1394-22-dev into libdc1394-dev if you are using Ubuntu 22.04 or upper version.

~$ sudo apt install build-essential cmake git pkg-config libgtk-3-dev \
 libavcodec-dev libavformat-dev libswscale-dev libv4l-dev \
 libxvidcore-dev libx264-dev libjpeg-dev libpng-dev libtiff-dev \
 gfortran openexr libatlas-base-dev python3-dev python3-numpy \
 libtbb2 libtbb-dev libdc1394-22-dev

 
