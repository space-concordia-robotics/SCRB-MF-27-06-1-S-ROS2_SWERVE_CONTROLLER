# SCRB-MF-27-06-1-S-ROS2_SWERVE_CONTROLLER
Repository for the development of the drive train ROS2 control controller. This includes the custom swerve drive, Ackermann and differential drive controllers.

# General Vibes
```mermaid
graph TD;
  joy_input["`Any Joystick
  Hardware`"]
  joy_node["`Joy_Node`"]
  joy["`\joy
  sensor_msgs/msg/Joy`"]
  joy_demux["`joy_demux_node`"]
  cmd_vel["`\cmd_vel
  geometry_msgs/msg/Twist`"]
  controller["`Drive Train Controllers
  ros2_control Controller`"]
  interface["`State and Control Interfaces
  ros2_control Hardware Interface`"]
  can["`CAN Frames
  Control Area Network Communication Protocol`"]
  sensors[Sensor Data]
  actuators[Actuator Command]
  
  joy_input --> joy_node
  joy_node --> joy
  joy --> joy_demux
  joy_demux --> cmd_vel
  cmd_vel --> controller
  controller <--> interface
  interface <--> can
  can --> actuators
  sensors --> can
```
All ready existing controllers to implement:
1. Differential Drive Controller
2. Ackermann Steering Controller

Custom controllers to implement:
1. Double Ackermann Steering Controller
2. Four-Wheel Independent Steering Controller

These controllers are the Drive Train Controllers
