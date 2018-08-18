cmake_minimum_required(VERSION 2.8.3)

project(irb_120_4)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
)
include_directories(
 include
  ${catkin_INCLUDE_DIRS}
)

catkin_package()

find_package(roslaunch)

foreach(dir config launch meshes urdf)
	install(DIRECTORY ${dir}/
		DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)
add_executable(state_1_publisher src/state_1_publisher.cpp)
target_link_libraries(state_1_publisher ${catkin_LIBRARIES})
