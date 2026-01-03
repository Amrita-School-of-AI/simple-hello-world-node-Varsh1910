add_executable(hello_node src/hello_node.cpp)

ament_target_dependencies(hello_node
  rclcpp
)

install(TARGETS
  hello_node
  DESTINATION lib/${PROJECT_NAME}
)
