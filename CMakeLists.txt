cmake_minimum_required(VERSION 3.8)
project(iturover_processing_assignment)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)

install(PROGRAMS
  src/filter_publisher.py
  DESTINATION lib/${PROJECT_NAME}
)

install(DIRECTORY
  launch
  rosbag
  DESTINATION share/${PROJECT_NAME}
)

ament_package()
