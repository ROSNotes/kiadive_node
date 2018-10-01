# 使用rqt
* 查看结点的状态信息：rostopic echo /turtle/pose
* 打开rqt查看结点运动的线性图像
* 打开地盘： roslaunch mx_bringup rbc_camera_start.launch
* 查看结点的关系图：rqt_graph

# ROS虚拟仿真平台 gazebo
* 打开机器人虚拟模型：roslaunch mx_urdf gazebo.launch
* 模拟和了解机器人的环境和基本属性
## 建图实例
* 启动环境并加载机器人: roslaunch turtlebot_gazebo turtlebot_world.launch
* 启动算法功能包:roslaunch turtlebot_gazebo gmapping_demo.launch
* 启动可视化工具并查看地图:roslaunch turtlebot_rviz_launchers view_navigation.launch
* 启动键盘控制功能:roslaunch turtlebot_teleop keyboard_teleop.launch
