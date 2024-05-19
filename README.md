- 运行micro_ros_agent，已经添加到开机启动项
```
ros2 run micro_ros_agent micro_ros_agent udp4 --port 8888
```

- 运行TF转换Launch-Bringup
```
source install/setup.bash
cd /workspace/ros2_robot/robot_ws
ros2 launch robot_bringup robot_bringup.launch.py
```
- 运行
```
ros2 launch rosbridge_server rosbridge_websocket_launch.xml
```

- 运行雷达
```
ros2 launch ydlidar_ros2_driver ydlidar_launch.py
```

- 使用SLAM_TOOLBOX完成建图
```
ros2 launch slam_toolbox online_async_launch.py
```

- 保存地图
```
ros2 run nav2_map_server map_saver_cli -t map -f fishbot_map
```
- 导航
```
ros2 launch robot_navigation2 navigation2.launch.py
```