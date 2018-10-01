#git use
*git clone http://github.com/username/project_name
*git status search_project
*git add
*git commit -m add_aim
*git push

#ros code
*ros master
*rosrun
*rosnode list
*rosnode info node_namcrea
*rosnode tab tab search_code
*rostopic find
*rostopic list
*rostopic -h
*rostopic type
*rostopic echo
*rostopic pub sender type message

#create a workspace
*在桌面创建一个文件夹:mkdir ros_ws/src -p
*进入ros_ws中的文件src初始化它：catkin_init_workspace;
×进入ros_ws中编译文件src:catkin_make;
×进入src，创建功能包：catkin_create_pkg gnb rospy;
*返回上一级，再次编译;
×告诉终端：source devel/setup.bash。
##建立launch文件
×建立launch文件夹：cd src/gnb; mkdir launch; cd launch/;
*建立launch文件：touch go.launch;
*编辑文件：gedit go.launch;
*编写launch文件;
*运行:roslaunch go.launch.
