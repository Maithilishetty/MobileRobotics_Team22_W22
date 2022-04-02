# Improving Tracking Abilities of Underwater ORB-SLAM3 and OKVIS Applications Via Image Enhancement
### EECS 568 Team 22

This repository contains the code for our final project for EECS 568: Mobile Robotics: Methods and Algorithms. Our project compared two different SLAM algorithms, ORB-SLAM3 and OKVIS. Then, we examined the effects of image enhancement on both algorithms.

Here (TODO) is a link to our paper.
  
Here (TODO) is a link to our final presentation and video.

There are three separate projects within this repository: ORB-SLAM3 with Image Enhancement, OKVIS with Image Enhancement, and Single Image Enhancement. We used the <a href="https://www.lirmm.fr/aqualoc/">Aqualoc dataset</a> to test all of our projects. Specifically, we used the harbor sequence 1 data.

## ORB-SLAM3 with Image Enhancement

TODO insert ORB-SLAM3 build instructions here.

## OKVIS with Image Enhancement

The second project is OKVIS modified to include image enhcncement capabilities. Here is a link to the original OKVIS repository. To build, first install dependencies:

- CMake: ```sudo apt-get install cmake```
- Google-Glog and GFlags: ```sudo apt-get install libgoogle-glog-dev```
- BLAS and LAPACK: ```sudo apt-get install libatlas-base-dev```
- Eigen3: ```sudo apt-get install libeigen3-dev```
- SuiteSparse and CXSparse: ```sudo apt-get install libsuitesparse-dev```
- Boost: ```sudo apt-get install libboost-dev libboost-filesystem-dev```
- OpenCV 4.2.0: ```sudo apt-get install libopencv-dev```

Then, from the root directory of the repository:

- Go into the OKVIS project: ```cd okvis```
- Create the build directory: ```mkdir build```
- Generate the Makefile: ```cmake ..```
- Build the project: ```make -j```

The project can now be run from the build directory as:

```./okvis_app_synchronous <path_to_okvis_config_yaml> <path_to_dataset> <image_enhancement_technique>```

To run the example dataset, you need to convert it to the correct okvis format:

TODO ADD INSTRUCTIONS TO CONVERT HARBOR DATASET TO OKVIS INPUT FORMAT

```./okvis_app_synchronous ../config/config_harbor.yaml <path_to_transformed_harbor_dataset>```

## Single Image Enhancement

Last is the image enhancement project, which is an extremely simple project that can be used to test various image enhancement algorithms on single images at a time, to see if features and contrast will be improved. First, install dependencies:

- CMake: ```sudo apt-get install cmake```
- OpenCV 4.2.0: ```sudo apt-get install libopencv-dev```

Then, from the root directory of this repository:

- Go into the Image Enhancement project: ```cd image_enhancement```
- Create the build directory: ```mkdir build && cd build```
- Generate the Makefile: ```cmake ..```
- Build the project: ```make -j```

The project can be run from the build directory as ```./image_enhancement <path_to_input_image> <path_to_output_image>```
