# How to install OpenCV on Ubuntu ([based on this guide](http://www.codebind.com/cpp-tutorial/install-opencv-ubuntu-cpp/))

## Step 1 – Updating Ubuntu
- `sudo apt-get update`  
- `sudo apt-get upgrade`  
  
## Step 2 – Install dependencies
- `sudo apt-get install build-essential cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev`  
- `sudo apt-get install python3.5-dev python3-numpy libtbb2 libtbb-dev`  
- `sudo apt-get install libjpeg-dev libpng-dev libtiff5-dev libjasper-dev libdc1394-22-dev libeigen3-dev libtheora-dev libvorbis-dev libxvidcore-dev libx264-dev sphinx-common libtbb-dev yasm libfaac-dev libopencore-amrnb-dev libopencore-amrwb-dev libopenexr-dev libgstreamer-plugins-base1.0-dev libavutil-dev libavfilter-dev libavresample-dev`  

**Fixes for possible errors:**  
1. "_Unable to locate package libjasper-dev_" ([source for solution](https://stackoverflow.com/questions/44468081/unable-to-locate-package-libjasper-dev))  
   * `sudo add-apt-repository "deb http://security.ubuntu.com/ubuntu xenial-security main"`  
   * `sudo apt update`  
   * `sudo apt install libjasper1 libjasper-dev`
2. "_Unable to locate package Python3.5-dev_" ([source for solution](https://askubuntu.com/questions/1052322/python3-5-dev-in-ubuntu-18-04))   
   * `sudo add-apt-repository ppa:deadsnakes/ppa`  
   * `sudo apt-get install python3.5-dev`  


## Step 3 –  Get OpenCV
- `sudo -s`  
- `cd /opt`  
- `git clone https://github.com/Itseez/opencv.git`  
- `git clone https://github.com/Itseez/opencv_contrib.git`  

## Step 4 – build and install OpenCV
- `cd opencv`  
- `mkdir release`  
- `cd release`  
- `cmake -D BUILD_TIFF=ON -D WITH_CUDA=OFF -D ENABLE_AVX=OFF -D WITH_OPENGL=OFF -D WITH_OPENCL=OFF -D WITH_IPP=OFF -D WITH_TBB=ON -D BUILD_TBB=ON -D WITH_EIGEN=OFF -D WITH_V4L=OFF -D WITH_VTK=OFF -D BUILD_TESTS=OFF -D BUILD_PERF_TESTS=OFF -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D OPENCV_EXTRA_MODULES_PATH=/opt/opencv_contrib/modules /opt/opencv/`  
- `make -j4`  
- `make install`  
- `ldconfig`  
- `exit`  
- `cd ~`  


# How to install Pylon camera software suite on Ubuntu ([based on this guide](https://www.baslerweb.com/en/products/cameras/area-scan-cameras/ace/aca1440-220uc/))


## Download the Basler Pylon Camera Software Suite ###
- Go to https://www.baslerweb.com/en/products/cameras/area-scan-cameras/ace/aca1440-220uc/
- Follow the link under Software, and find "pylon 6.3.0 Camera Software Suite Linux x86 (64 Bit)" [Direct link](https://www.baslerweb.com/en/sales-support/downloads/software-downloads/software-pylon-6-3-0-linux-x86-64bit/) 
  - Or choose a newer version
  - [Direct dowload link](https://www.baslerweb.com/fp-1636374975/media/downloads/software/pylon_software/pylon_6.3.0.23157_x86_64_setup.tar.gz)


## Installation using tar.gz files ###
_This part is copied from the installation instructions in the downloaded material_

This installation procedure assumes that you are going to install the
pylon Camera Software Suite in the /opt/pylon directory. If you choose
to install in a different directory, you'll have to modify the 
directory names accordingly.
Note: Root permissions are needed to write to /opt.

To install the pylon 6 Camera Software Suite in /opt/pylon follow these steps:

  1. Change to the directory that contains the pylon setup tar.gz archive that you downloaded from the Basler website.
     - `cd ~Downlaods`

  2. Extract the setup tar.gz archive into a directory of your choice
     - `mkdir ./pylon_setup`
     - `tar -C ./pylon_setup -xzf ./pylon_*_setup.tar.gz`

  3. Change to the directory into which you extracted the setup tar.gz:
     - `cd ./pylon_setup`
     
  4. Extract the pylon SDK into /opt/pylon:
     - `sudo tar -C /opt/pylon -xzf ./pylon_*.tar.gz`

  5. Change access rights of the pylon folder:
     - `sudo chmod 755 /opt/pylon`


## Test
- Use the small program in [this repo](https://github.com/anders-lind/Tests/tree/main/Test%20of%20Pylon%20with%20OpenCV), to test if Pylon is working (requiers OpenCV and a Basler camera)
