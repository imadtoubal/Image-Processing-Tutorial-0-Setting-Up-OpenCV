# Installation on OSX

This tutorial requires a basic level of bash scripting and using the terminal.

## Compiler

First, you will need to make sure a C++ compiler is installed on your machine. 
For OSX, clang compiler comes with XCode and is very common on the platform. 
Visit [Apple's docs](https://developer.apple.com/support/xcode/) for 
installation instructions.

## Installing Homebrew

[Homebrew](https://brew.sh/) is a common OSX package manager and it will 
simplify the next step. As stated in the official website, Homebrew is installed 
using the following command:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

## Installing CMake
[CMake](https://cmake.org/) is another tool that we will use to simplify 
developing for C++ using the OpenCV library. Using Homebrew, you can simply 
install CMake with the following command:

```bash
brew install cmake
```

## Installing OpenCV from Source with CMake

The following list of commands will download the OpenCV repository from GitHub 
and build it:

```bash
# Move to the directory in which you want to install OpenCV
mkdir ~/opencv
cd ~/opencv 

# Install wget to download from the terminal
brew install wget

# Download and unpack sources
wget -O opencv.zip https://github.com/opencv/opencv/archive/master.zip
unzip opencv.zip
rm opencv.zip

# Create build directory
mkdir -p build && cd build

# Configure
cmake  ../opencv-master

# Build
cmake --build .
```

## Test your installation

This repository comes with a basic program to display an image. 

### Compile the program
In order to compile the program, you can execute the following commands:
```bash
cmake .
make
```

### Executing the program
Executing the program requires passing a command line argument that is the path
of the test image you would like to display. For convenience `Lenna.png` is 
provided. Below is a sample execution command:
```bash
./DisplayImage Lenna.png
```

You should see a popup window with the image, pressing any button on your 
keyboard will close that window.
