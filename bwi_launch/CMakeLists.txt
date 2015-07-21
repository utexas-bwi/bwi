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
  roslaunch_add_file_check(launch)
endif()
