cmake_minimum_required(VERSION 2.8.3)
project(usb_cam_subscriber)

find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  image_transport
  roscpp
  std_msgs
)
find_package(OpenCV REQUIRED)

catkin_package(

  CATKIN_DEPENDS cv_bridge image_transport roscpp std_msgs
  DEPENDS OpenCV 
)


include_directories(

  ${catkin_INCLUDE_DIRS}
  ${OpenCV_INCLUDE_DIRS}
)


add_executable(${PROJECT_NAME} src/usb_cam_subscriber_node.cpp)

target_link_libraries(${PROJECT_NAME}
        ${catkin_LIBRARIES} ${OpenCV_LIBRARIES})


