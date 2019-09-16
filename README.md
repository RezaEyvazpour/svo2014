# Intro
This repository aims to reduce the minimum effort needed to build and debug the official SVO 2014(non-ROS) implementation on an up-to-date system with recent releases of `OpenCV`, `Eigen` and `Boost`.  
Note that libraries `sophus`, `vikit-common` and `fast` are unified with the main code `svo`, so it could be a lot easier to debug and understand how they work together.

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
  
And to run all of the unit tests, hit:
```
make test
```

# Reference
1. [uzh-rpg/rpg_svo](https://github.com/uzh-rpg/rpg_svo)