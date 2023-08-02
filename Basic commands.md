## Remove a folder
- `rm -r -f some/folder/path`


## Moving a folder or file
- `mv path/to/file/or/folder new/path/to/folder/or/file` 


## Rename a folder
Renaming a folder is done by "moving" it, and giving it a new name
- `mv path/to/old_name path/to/new_name`


## Install a .deb file
- `sudo apt install ./example-file-name.deb`


## Install a .run file
- Make it executeable
  - `chmod +x some-app.run`
- Run it
  - `sudo ./some-app.run`


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


## Extract file.tar.gz archive
- `tar -xf archive.tar.gz`

## Add folder to $PATH
- Add "/new/path" to path file
- sudo nano /etc/environment
https://askubuntu.com/questions/500775/permanent-path-variable


# Git in terminal
## Clone a directory
Download all files from a Git directory
- `cd ~/some/dir`
- `git clone https://github.com/anders-lind/Ubuntu-guides`

## Basic commands
- `git status`
- `git pull`
- `Git commit`
- `git push`
