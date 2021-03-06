cmake_minimum_required(VERSION 2.8.3)
project(activity_exploration)

find_package(catkin REQUIRED COMPONENTS
  roslib
  rospy
  std_msgs
  std_srvs
  mongodb_store
  region_observation
  strands_executive_msgs
  strands_navigation_msgs
  scene_temporal_patterns
  people_temporal_patterns
  activity_temporal_patterns
  exploration_bid_manager
)

catkin_python_setup()

################################################
## Declare ROS messages, services and actions ##
################################################

add_message_files(
  FILES
  ExplorationChoice.msg
)

add_service_files(
  FILES
  ChangeMethodSrv.srv
)

## Generate actions in the 'action' folder
# add_action_files(
#   FILES
#   Action1.action
#   Action2.action
# )

generate_messages(
  DEPENDENCIES
  std_msgs
)

###################################
## catkin specific configuration ##
###################################

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES activity_exploration
  CATKIN_DEPENDS region_observation roslib rospy strands_executive_msgs strands_navigation_msgs people_temporal_patterns activity_temporal_patterns std_msgs std_srvs exploration_bid_manager scene_temporal_patterns mongodb_store
#  DEPENDS system_lib
)

###########
## Build ##
###########

include_directories(
  ${catkin_INCLUDE_DIRS}
)

#############
## Install ##
#############

# install(PROGRAMS
#   scripts/counting_manager.py
#   src/region_observation/observe.py
#   src/periodic_poisson_processes/people_poisson.py
#   DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
# )
# install(DIRECTORY launch
#     DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
# )
