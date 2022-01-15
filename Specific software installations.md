# What is this?
- This is a collection of guides for installing different software on Ubuntu.
- It is created primarilay as a way for me personally to minimize time spent installing sofware, i have succesfully installed before.
- You are free to use theses guides and i hope they can help you.

<!--- Vertical blanc space --->
<img src="https://user-images.githubusercontent.com/32484749/149629392-40155cb0-fccf-481f-933e-d2d0748ce457.png" height="100" />






# How to create a modded minecraft server with Forge
- A vanilla Minecraft client installation is required


### Step 1 - Download java and byobu
- `sudo apt install openjdk-8-jdk`


### Step 2 - Find the correct version of Minecraft
- I want to install the mods "[The Twillight Forest](https://www.curseforge.com/minecraft/mc-mods/the-twilight-forest/files?sort=-game-version)", "[ConnectedTexturesMod](https://www.curseforge.com/minecraft/mc-mods/ctm/files?sort=-game-version)", "[mantle (required by Tinkers Construct)](https://www.curseforge.com/minecraft/mc-mods/mantle/download/2713386)" and "[Tinkers Construct](https://www.curseforge.com/minecraft/mc-mods/tinkers-construct/files?sort=-game-version)"
- Their highest shared Minecraft version is 1.12.2


### Step 3 - Download the mods and the Forge installer 
- Download the correct version of the mods using your browser
  - [https://www.curseforge.com/minecraft/mc-mods/the-twilight-forest/files?sort=-game-version](https://www.curseforge.com/minecraft/mc-mods/the-twilight-forest/files?sort=-game-version)
  - [https://www.curseforge.com/minecraft/mc-mods/ctm/files?sort=-game-version](https://www.curseforge.com/minecraft/mc-mods/ctm/files?sort=-game-version)
  - [https://www.curseforge.com/minecraft/mc-mods/tinkers-construct/files?sort=-game-version](https://www.curseforge.com/minecraft/mc-mods/tinkers-construct/files?sort=-game-version)
  - [https://www.curseforge.com/minecraft/mc-mods/mantle/download/2713386](https://www.curseforge.com/minecraft/mc-mods/mantle/download/2713386)
-  Download the Forge installer manually or using the wget-command with a direct link to the download
  - https://files.minecraftforge.net/net/minecraftforge/forge/
  - `wget https://maven.minecraftforge.net/net/minecraftforge/forge/1.12.2-14.23.5.2859/forge-1.12.2-14.23.5.2859-installer.jar`


### step 4 - Install Forge client and server
- Create and enter the directory you want to store the server
  - `mkdir ~/minecraft_Forge_server`
  - `cd ~/minecraft_Forge_server`
- Move the Forge installer into this directory
  - `mv ~/Downloads/forge-1.12.2-14.23.5.2859-installer.jar .`
- Install the server by running the installation file with "--installServer" as parameter
  - `java -jar forge-1.12.2-14.23.5.2859-installer.jar -installServer`
- Install the client by running the installation file
  - `java -jar forge-1.12.2-14.23.5.2859-installer.jar`
  - Choose "Install client"
  - The directory of your Minecraft installation is probably the default `/home/username/.minecraft`
- Delete the Forge installer as it is no longer required
  - `rm forge-1.12.2-14.23.5.2859-installer.jar`
  - `rm forge-1.12.2-14.23.5.2859-installer.jar.log 
- Run the server file to initialize folders (Error fix in footnote *1* of this guide)
  - `java -Xmx1024M -Xms1024M -jar forge-1.12.2-14.23.5.2859.jar nogui`
  - This should have created a "mods" and a "logs" folder and a "eula.txt" file


### Step 5 - Install the mods
- Install the mods on the server by moving them to the servers mods folder
  - `mv -t ~/minecraft_Forge_server/mods ~/Downloads/CTM-MC1.12.2-1.0.2.31.jar  ~/Downloads/TConstruct-1.12.2-2.13.0.183.jar  ~/Downloads/twilightforest-1.12.2-3.10.1013-universal.jar ~/Downloads/Mantle-1.12-1.3.3.55.jar`
- Install the mods on the client by copying them to the client mods folder
  - `cp -t ~/.minecraft/mods ~/minecraft_Forge_server/mods/CTM-MC1.12.2-1.0.2.31.jar  ~/minecraft_Forge_server/mods/TConstruct-1.12.2-2.13.0.183.jar  ~/minecraft_Forge_server/mods/twilightforest-1.12.2-3.10.1013-universal.jar ~/minecraft_Forge_server/mods/Mantle-1.12-1.3.3.55.jar`


### Step 6 - Start and join the server
- Accept the EULA
  - `nano eula.txt`
  - Make sure a line in the file says "eula=true"
- Start the server
  - `java -Xmx1024M -Xms1024M -jar forge-1.12.2-14.23.5.2859.jar nogui`
- Join the server by starting normal Minecraft and choosig the Forge installation
- Then join the server as you normally would normally

## Errors and how to fix them
1. "A problem occurred running the Server launcher.java.lang.reflect.InvocationTargetException"
   - Switch to java version 8
     - sudo update-alternatives --config java

<!--- Vertical blanc space --->
<img src="https://user-images.githubusercontent.com/32484749/149629392-40155cb0-fccf-481f-933e-d2d0748ce457.png" height="100" />






# How to install OpenCV 
[Based on this guide](http://www.codebind.com/cpp-tutorial/install-opencv-ubuntu-cpp/)

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

<!--- Vertical blanc space --->
<img src="https://user-images.githubusercontent.com/32484749/149629392-40155cb0-fccf-481f-933e-d2d0748ce457.png" height="100" />






# How to install Pylon camera software suite
 [Based on this guide](https://www.baslerweb.com/en/products/cameras/area-scan-cameras/ace/aca1440-220uc/)

## Download the Basler Pylon Camera Software Suite ###
- Go to https://www.baslerweb.com/en/products/cameras/area-scan-cameras/ace/aca1440-220uc/
- Follow the link under Software, and find "pylon 6.3.0 Camera Software Suite Linux x86 (64 Bit)" [Direct link](https://www.baslerweb.com/en/sales-support/downloads/software-downloads/software-pylon-6-3-0-linux-x86-64bit/) 
  - Or choose a newer version
  - [Direct dowload link](https://www.baslerweb.com/fp-1636374975/media/downloads/software/pylon_software/pylon_6.3.0.23157_x86_64_setup.tar.gz)


## Installation using tar.gz files ##
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

## Problems
- Working library, but not showing up in projects or pylonviewer
  - Make sure the camaera is connected via a USB-3 connection
  - Try restarting 
  - Try installing via the .deb file


## Test
- Run the command `/opt/pylon/bin/pylonviewer` and you sould be able to select the camera under USB
- Use the small program in [this repo](https://github.com/anders-lind/Tests/tree/main/Test%20of%20Pylon%20with%20OpenCV), to test if Pylon is working (requiers OpenCV and a Basler camera)

<!--- Vertical blanc space --->
<img src="https://user-images.githubusercontent.com/32484749/149629392-40155cb0-fccf-481f-933e-d2d0748ce457.png" height="100" />






# How to install video codecs
[Based on this guide](https://linuxhint.com/install_multimedia_codecs_ubuntu/)
- 'sudo apt install ubuntu-restricted-extras'
