# 硬件简介
* 打开终端：open Terminal
* 启动雷达：roslaunch mx_bringup rbc_lidar_start.launch
* 启动相机：roslaunch mx_bringup rbc_camera_start.launch
* 颜色追踪：roslaunch mx_apps opencv3_tracker.launch color:=true
## 激光雷达建立地图
* 打开雷达：roslaunch mx_bringup rbc_lidar_start.launch
* 通过键盘控制地图并打开视图：roslaunch mx_nav gmapping_demo.launch rviz-view:=1
## 语音交互
* roslaunch voice_bringup voice_bringup.launch

# linux基础命令
* 查看当前目录：pwd
* 改变当前目录：cd
* 根目录：/
* 用户目录：~
* 返回到上一级目录：cd ..
* 清空屏幕：clear
* 查看当前目录的文件列表：ls
* 创建文件：touch
* 创建文件夹：mkdir
* 删除文件：rm
* 查看指令的使用方法：--help / man
