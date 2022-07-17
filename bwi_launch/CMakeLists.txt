cmake_minimum_required(VERSION 2.8.3)
project(bwi_launch)
find_package(catkin REQUIRED)
catkin_package()

install(DIRECTORY launch/
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch)

install(DIRECTORY config/
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch)

catkin_install_python(PROGRAMS scripts/multi_robot_launcher
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

# unit tests are enabled selectively
if (CATKIN_ENABLE_TESTING)
  find_package(roslaunch REQUIRED)

  ## Test individual files that do work, restore testing of the
  #  rest when segway_v3 packages have been released.
  #roslaunch_add_file_check(launch)
  roslaunch_add_file_check(launch/multi_robot_simulation.launch)
  roslaunch_add_file_check(launch/segbot_ns_kr.launch)
  roslaunch_add_file_check(launch/segbot_v1.launch)
  roslaunch_add_file_check(launch/segbot_v2.launch)
  roslaunch_add_file_check(launch/segbot_v2.arm.launch)
  #roslaunch_add_file_check(launch/segbot_v3.launch)
  roslaunch_add_file_check(launch/simulation_v2.launch)
  roslaunch_add_file_check(launch/simulation_v2.arm.launch)
  #roslaunch_add_file_check(launch/simulation_v3.launch)
endif()
