# How to compile and run c++ programs
[Based on this guide](https://code.visualstudio.com/docs/languages/cpp)
  - Download MinGW-w64
    - https://www.msys2.org/
  - Open 'msys2_shell.cmd' in the newly created 'msys64'-folder
  - Update MSYS2 with pacman 
    - `pacman -Syu`
  - Update the rest of the base packages
    - Run "MSYS2 MSYS" from Start menu.
    - `pacman-Su`
  - install tools and the mingw-w64 GCC
    - `pacman -S --needed base-devel mingw-w64-x86_64-toolchain`
  - Add minGW to Windows path
    - Add `C:\msys64\mingw64\bin` (or your equivalent) to PATH
  - Check your MinGW-w64 installation with these commands in Windows Command Prompt
    - ``g++ --version``
    - ``gdb --version``
  - Now create a C++ program called helloworld.cpp
  - Compile the program with g++ from a command prompt in the same directory as the program [For more compilation options](https://courses.cs.washington.edu/courses/cse373/99au/unix/g++.html)
    - `g++ -o exeName helloworld.cpp`
  - This creates an executable called "exeName"
  - Execute "exeName" from command prompt
    - `.\exename` or `.\exename.exe`


<!--- Vertical blanc space --->
<img src="https://user-images.githubusercontent.com/32484749/149629392-40155cb0-fccf-481f-933e-d2d0748ce457.png" height="100" />


# How to uninstall Cortana
[Based on this guide](https://www.tomsguide.com/news/how-to-uninstall-cortana)
- Open Windows PowerShell as administator
  - `Get-AppxPackage -allusers Microsoft.549981C3F5F10 | Remove-AppxPackage`
