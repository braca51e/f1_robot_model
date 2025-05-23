# f1_robot_model

Car simulator f1 foxy tenth in ROS2

## You must install: 

```bash
sudo apt install ros-<ros2-distro>-joint-state-publisher-gui
sudo apt install ros-<ros2-distro>-xacro
sudo apt install ros-<ros2-distro>-gazebo-ros-pkgs
sudo apt install ros-<ros2-distro>-ackermann-msgs
sudo apt install ros-<ros2-distro>-imu-tools  # For IMU visualization and tools
```

## Run Locally

Write in shell #1 in the ros2_ws

```bash
source /opt/ros/foxy/setup.bash #for ros2 foxy
source /opt/ros/humble/setup.bash #for ro2 humble
colcon build --packages-select f1_robot_model
source install/setup.bash
ros2 launch f1_robot_model display.launch.py
```

Write in shell #2
```bash
source /opt/ros/foxy/setup.bash
ros2 topic pub /ackermann_cmd ackermann_msgs/msg/AckermannDriveStamped "{header: {stamp: {sec: 0, nanosec: 0}, frame_id: 'base_link'}, drive: {speed: 0.0, steering_angle: 0.5}}"
```
## Distribution
```bash
f1_robot_model/
|-- src/
|   |-- ackermann_to_cmd_vel.cpp
|-- world/
|   |-- empty_world.sdf
|   |-- my_world.sdf
|-- urdf/
|   |-- macros.xacro
|   |-- materials.xacro
|   |-- racecar.gazebo
|   |-- racecar.urdf
|-- rviz/
|   |-- urdf_config.rviz
|-- launch/
|   |-- display.launch.py
|-- CMakeLists.txt
|-- package.xml
```

## Authors

- [@armando-genis](https://github.com/armando-genis)