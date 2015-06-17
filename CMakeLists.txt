cmake_minimum_required(VERSION 2.8.3)
project(object_recognition_clusters)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs object_recognition_msgs roscpp
  rospy tf ecto ecto_ros pcl_ros
  message_generation
  sensor_msgs
)




catkin_python_setup()

## Generate services in the 'srv' folder
add_service_files(
  FILES
	FindClusterBoundingBox.srv
	FindClusterBoundingBox2.srv
)

generate_messages(
   DEPENDENCIES
   std_msgs
   sensor_msgs
   geometry_msgs
)

catkin_package()

add_subdirectory(src)

include_directories(
  ${catkin_INCLUDE_DIRS}
)
