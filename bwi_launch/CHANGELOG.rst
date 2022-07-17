^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package bwi_launch
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

0.3.3 (2015-08-06)
------------------

0.3.2 (2015-08-06)
------------------
* removed segbot_v2.arm.launch as mico driver is not yet
  released. Launch file moved to segbot_arm_launch experimental package.
* included bwi_logging/launch/record.launch into segbot_v2.launch
* added main, all-in-one launch file for the segbot_v2 with arm
* parameterized the single robot launch file being launched by the
  multi_robot_launcher
* now use default level on all launch file, in addition use
  multi_robot_launcher which can launch multiple robots in a scripted
  manner.
* Contributors: Jivko Sinapov, Piyush Khandelwal, Shiqi Zhang

0.3.1 (2015-03-31)
------------------
* updated launch files to account for upcoming amcl.launch change.
* updated launch file to automatically start the planner/reasoner in simulation mode.
* Contributors: Piyush Khandelwal

0.3.0 (2015-03-24)
------------------
* bwi_launch: add build dependencies for launch checking references (`#16 <https://github.com/utexas-bwi/bwi/issues/16>`_)
  do not depend on segbot_gazebo twice
* bwi_launch: dependency and launch file cleanup
  partial fix for `#16 <https://github.com/utexas-bwi/bwi/issues/16>`_
* added launch files for segbot v1 and v2 to bwi_launch
* Contributors: Jack O'Quin, Piyush Khandelwal

0.2.1 (2014-05-14)
------------------

0.2.0 (2014-04-24)
------------------
* release to Hydro
* make a separate bwi_launch package
* Contributors: Jack O'Quin
