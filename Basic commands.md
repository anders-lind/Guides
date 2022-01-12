## Install a .deb file
- `sudo apt install ./example-file-name.deb`



## Make a file executable (ex a .appimage file)
- `chmod a+x example-file-name.AppImage`



## Switch between different versions of Java
- `sudo update-alternatives --config java`



## Create a CMakeLists project
Create a src- og build-folder for the CMake project
- `mkdir build`
- `mkdir src`

Enter the build folder and make the project
- `cd build/`
- `cmake DCMAKE_BUILD_TYPE=Debug ../src/`


