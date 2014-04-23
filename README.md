# bwi

This repository contains top-level ROS packages for the Building Wide
Intelligence (BWI) project of the University of Texas at Austin
Computer Science Department.

## BWI Repository Hierarchy

Packages contained in various released BWI repostories may depend on
other packages at the same or lower levels.  Dependencies on packages
from higher-level repositories are not permitted.

From top to bottom, the released repositories are:

 * [bwi](http://wiki.ros.org/bwi)
 * [bwi_planning](http://wiki.ros.org/bwi_planning)
 * [clasp](http://wiki.ros.org/clasp)
 * [segbot_simulation](http://wiki.ros.org/segbot_simulation)
 * [segbot_apps](http://wiki.ros.org/segbot_apps)
 * [segbot](http://wiki.ros.org/segbot)
 * [bwi_common](http://wiki.ros.org/bwi_common)

## Installation

### From Source

To install all the BWI source components:

First, [install ROS Hydro](http://wiki.ros.org/hydro/Installation/Ubuntu).

Next, clone the source repositories:
```
$ source /opt/ros/hydro/setup.bash
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws
$ wstool init src https://raw.githubusercontent.com/utexas-bwi/bwi/master/rosinstall/bwi.rosinstall
```

Install all dependencies:
```
$ rosdep install --from-paths src --ignore-src --rosdistro hydro -y
```

Then, build everything:
```
$ catkin_make
$ source devel/setup.bash
```

### From Binary Packages

*Not yet available.  Coming soon.*
```
$ sudo apt-get install ros-hydro-bwi
```
