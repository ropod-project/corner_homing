cmake_minimum_required(VERSION 2.8.3)
project(corner_homing)

find_package(catkin REQUIRED COMPONENTS
    rospy
    actionlib
    message_generation
)

add_action_files(
  DIRECTORY ros/action
  FILES
    CornerHoming.action
)

generate_messages(
  DEPENDENCIES
    std_msgs
    actionlib_msgs
)

catkin_package(
  CATKIN_DEPENDS
    rospy
    message_runtime
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

install(PROGRAMS
  ros/scripts/corner_homing
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}/scripts
)

install(DIRECTORY ros/launch/
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
)
