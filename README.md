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
 * [segbot](http://wiki.ros.org/segbot)
 * [bwi_common](http://wiki.ros.org/bwi_common)

## Installation

### From Source

You can install all the BWI components normally built from source on
either ROS Indigo or Kinetic.

First, install ROS
[Indigo](http://wiki.ros.org/indigo/Installation/Ubuntu), or
[Kinetic](http://wiki.ros.org/indigo/Installation/Ubuntu).

The Kinetic version is only supported on Ubuntu Xenial, and is
only partially functional.

Then, make sure the ROS_DISTRO environment variable is set correctly:

```
echo $ROS_DISTRO
```

It may already be.  If not, issue the appropriate one of these two
shell commands:

```
$ export ROS_DISTRO=kinetic
```
or
```
$ export ROS_DISTRO=melodic
```

Next, clone the source repositories:
```
$ source /opt/ros/$ROS_DISTRO/setup.bash
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws
$ wstool init src https://raw.githubusercontent.com/utexas-bwi/bwi/master/rosinstall/$ROS_DISTRO.rosinstall
```

Install all dependencies:
```
$ rosdep update
$ rosdep install --from-paths src --ignore-src --rosdistro $ROS_DISTRO -y
```

Then, build everything. On a slow computer:
```
$ catkin build -j2 
$ source devel/setup.bash
```

Or on a fast computer:
```
$ catkin build -j6 
$ source devel/setup.bash
```
Or you can adjust the job limit as you see fit.


Note that the **catkin build** command from the **python-catkin-tools**
package is *required* for building on ROS Kinetic and Melodic. On ROS Indigo, you
can still use **catkin_make** instead, although the newer build tool
is recommended.

### For Version 4 Robot

The V4 base uses slightly different values for some environment variables. It's important to export them into your environment after you source the workspace. Add the convenience function sws to the bottom of your .bashrc file found at ~/.bashrc.
```
sws() {
  source ~/catkin_ws/devel/setup.bash
  export SEGWAY_INTERFACE_ADDRESS=10.66.171.1
  export SEGWAY_IP_ADDRESS=10.66.171.5
  export SEGWAY_IP_PORT_NUM=8080
  export SEGWAY_BASE_PLATFORM=RMP_110
  export SEGWAY_PLATFORM_NAME=RMP_110
}
sws
```
After building your workspace or packages, instead of using "source /devel/setup.bash" , simply call the function above by typing:
```
$ sws
```
