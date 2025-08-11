cmake_minimum_required(VERSION 3.8)
project(mujoco_ros_sim_msgs)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(sensor_msgs REQUIRED)

set(MSG_FILES
  "msg/NamedFloat64Array.msg"
  "msg/JointDict.msg"
  "msg/SensorDict.msg"
  "msg/CtrlDict.msg"
  "msg/NamedImage.msg"
  "msg/ImageDict.msg"
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${MSG_FILES}
  DEPENDENCIES std_msgs builtin_interfaces sensor_msgs
)

ament_export_dependencies(rosidl_default_runtime)
ament_package()
