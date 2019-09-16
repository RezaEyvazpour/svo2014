# Intro
This repository aims to reduce the minimum effort needed to build and debug the official SVO 2014 non-ROS implementation on an up-to-date system with recent releases of `OpenCV`, `Eigen` and `Boost`.

# Prepare Data
1. Hit `mkdir data` inside the root directory of this repository.
1. Download sample dataset from [here](http://rpg.ifi.uzh.ch/datasets/sin2_tex2_h1_v8_d.tar.gz).
1. Extract the archive and copy the folder into the `data` directory. 

# How to Build and Run
Simply hit:
```
mkdir build
cd build
cmake ..
make
```
  
To run all of the unit tests, hit:
```
make test
```