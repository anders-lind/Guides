## Remove a folder
- `rm -r -f some/folder/path`

## Moving a folder or file
- `mv path/to/file/or/folder new/path/to/folder/or/file` 

## Rename a folder
Renaming a folder is done by "moving" it, and giving it a new name
- `mv path/to/old_name path/to/new_name`

## Install a .deb file
- `sudo apt install ./example-file-name.deb`


## Clone a directory from Github
Download all files from a Git directory
- `cd ~/some/dir`
- `git clone https://github.com/anders-lind/Ubuntu-guides`


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


