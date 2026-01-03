cmake_minimum_required(VERSION 3.8)
project(hello_world_pkg)

# Enable warnings
if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# Find dependencies
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)

# Create executable
add_executable(hello_node src/hello_node.cpp)

# Link dependencies
ament_target_dependencies(hello_node
  rclcpp
)

# Install executable
install(TARGETS
  hello_node
  DESTINATION lib/${PROJECT_NAME}
)

# Package export
ament_package()
