# 注意事项
测试环境： ubuntu20, ros noetoc

# 下载编译
```shell
sudo apt-get update
sudo apt-get install -y python3-wstool python3-rosdep ninja-build stow
sudo rosdep init
rosdep update
rosdep install --from-paths src --ignore-src --rosdistro=$ROS_DISTRO -y
./src/cartographer/scripts/install_abseil.sh
catkin_make_isolated
```

# 使用方法
- Source the workspace for each terminal
```shell
source ./devel_isolated/setup.bash
```
- Launch the Gazebo simulation
```shell
 export HUSKY_LMS1XX_ENABLED=1; roslaunch husky_gazebo husky_playpen.launch
```
- Launch the Cartographer node to begin SLAM
```shell
roslaunch husky_cartographer_navigation cartographer_demo.launch
```
- Launch Rviz
```shell
roslaunch husky_viz view_robot.launch
```

# 结果图
![alt text](image.png)

# 参考链接
Cartographer:
https://google-cartographer-ros.readthedocs.io/en/latest/compilation.html

husky_cartographer:
https://github.com/husky/husky_cartographer_navigation
