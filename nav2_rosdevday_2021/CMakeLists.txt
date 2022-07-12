cmake_minimum_required(VERSION 3.8)
project(nav2_rosdevday_2021)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(ament_cmake_python REQUIRED)
find_package(rclcpp REQUIRED)
find_package(rclpy REQUIRED)

install(DIRECTORY launch DESTINATION share/${PROJECT_NAME})
install(DIRECTORY maps DESTINATION share/${PROJECT_NAME})
install(DIRECTORY params DESTINATION share/${PROJECT_NAME})
install(DIRECTORY scripts DESTINATION share/${PROJECT_NAME})
install(DIRECTORY worlds DESTINATION share/${PROJECT_NAME})

install(PROGRAMS
  scripts/inspection_demo.py
  scripts/nav_through_poses_demo.py
  scripts/nav_to_pose_demo.py
  scripts/picking_demo.py
  scripts/robot_navigator.py
  scripts/security_demo.py
  scripts/waypoint_follower_demo.py
  DESTINATION lib/${PROJECT_NAME}
)

ament_package()
