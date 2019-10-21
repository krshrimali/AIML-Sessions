# OpenCV Session - Installation Details

## Building OpenCV from Source: For C++ and Python

**For Linux**:

1. Install git: `sudo apt-get install git`
2. 
```
cd ~/Documents/
sudo apt -y update
sudo apt -y upgrade

sudo apt -y remove x264 libx264-dev
 
## Install dependencies
sudo apt -y install build-essential checkinstall cmake pkg-config yasm
sudo apt -y install git gfortran
sudo apt -y install libjpeg8-dev libpng-dev
 
sudo apt -y install software-properties-common
sudo add-apt-repository "deb http://security.ubuntu.com/ubuntu xenial-security main"
sudo apt -y update
 
sudo apt -y install libjasper1
sudo apt -y install libtiff-dev
 
sudo apt -y install libavcodec-dev libavformat-dev libswscale-dev libdc1394-22-dev
sudo apt -y install libxine2-dev libv4l-dev
cd /usr/include/linux
sudo ln -s -f ../libv4l1-videodev.h videodev.h
```
3. `cd ~/Documents/`
4. 
```
sudo apt -y install libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev
sudo apt -y install libgtk2.0-dev libtbb-dev qt5-default
sudo apt -y install libatlas-base-dev
sudo apt -y install libfaac-dev libmp3lame-dev libtheora-dev
sudo apt -y install libvorbis-dev libxvidcore-dev
sudo apt -y install libopencore-amrnb-dev libopencore-amrwb-dev
sudo apt -y install libavresample-dev
sudo apt -y install x264 v4l-utils
```
5. 
```
sudo apt -y install libprotobuf-dev protobuf-compiler
sudo apt -y install libgoogle-glog-dev libgflags-dev
sudo apt -y install libgphoto2-dev libeigen3-dev libhdf5-dev doxygen

sudo apt -y install python3-dev python3-pip
sudo -H pip3 install -U pip numpy
sudo apt -y install python3-testresources
```
6. 
```
git clone https://github.com/opencv/opencv.git
cd opencv
git checkout 4.1.0
cd ..
 
git clone https://github.com/opencv/opencv_contrib.git
cd opencv_contrib
git checkout 4.1.0
cd ..
```
7. `cd opencv && mkdir build && cd build`
8. 
```
cmake -D CMAKE_BUILD_TYPE=RELEASE \
            -D INSTALL_C_EXAMPLES=OFF \
            -D INSTALL_PYTHON_EXAMPLES=OFF \
            -D WITH_TBB=ON \
            -D WITH_V4L=ON \
        -D WITH_QT=ON \
        -D WITH_OPENGL=ON \
        -D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules \
        -D BUILD_EXAMPLES=OFF ..
```
9. `make -j$(nproc)`
10. `make install`

**For Windows**:

Note: This requires Microsoft Visual Studio pre-installed with C++ configuration.

1. Go to: https://github.com/opencv/opencv/releases and download https://github.com/opencv/opencv/releases/download/4.1.0/opencv-4.1.0-vc14_vc15.exe
2. Install OpenCV

**For Mac**:

1. Follow this blog: https://www.pyimagesearch.com/2018/08/17/install-opencv-4-on-macos/
