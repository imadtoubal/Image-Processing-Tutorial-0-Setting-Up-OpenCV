# Installation on Linux

This tutorial requires a basic level of bash scripting and using the terminal.

## Compiler

First, you will need to make sure a C++ compiler is installed on your machine. 
Ensure that g++ is installed using the following command:
```bash
g++ -v
```

If not you can run the following command from the terminal window to update the Ubuntu package lists. An out-of-date Linux distribution can sometimes interfere with attempts to install new packages.

```bash
sudo apt-get update
```
Next install the GNU compiler tools and the GDB debugger with this command:

```bash
sudo apt-get install build-essential gdb
```

## Installing CMake
[CMake](https://cmake.org/) is another tool that we will use to simplify 
developing for C++ using the OpenCV library. You can simply 
install CMake by following the [official documentation](https://cmake.org/install/).

## Installing OpenCV from Source with CMake

The following list of commands will download the OpenCV repository from GitHub 
and build it:

```bash
# Move to the directory in which you want to install OpenCV
mkdir ~/opencv
cd ~/opencv 

# Install wget to download from the terminal
apt-get install wget

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
./DisplayImage Lenna.jpg
```

You should see a popup window with the image, pressing any button on your 
keyboard will close that window.
