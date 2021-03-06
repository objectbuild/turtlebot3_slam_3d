## Turtlebot3 3D-SLAM demo using RTAB-Map with Jetson TX2 and ZED Mini

#### Quick Start:

Install `rtabmap_ros`:
```
sudo apt install ros-kinetic-rtabmap-ros
```

Setup ZED Mini following instructions on https://github.com/stereolabs/zed-ros-wrapper/ .

Then, setup the workspace:
```
mkdir catkin_ws/src -p
cd catkin_ws/src
git clone https://github.com/ROBOTIS-JAPAN/turtlebot3_slam_3d.git
git clone https://github.com/ROBOTIS-JAPAN/turtlebot3_slam_3d.git
rosdep install -y -r --from-paths . --ignore-src
cd ../
catkin build
source devel/setup.bash
```

#### Launch Files:

Sample mapping bag file can be executed with:
```
roslaunch turtlebot3_slam_3d demo_bag.launch
```

Map is saved to `~/.ros/rtabmap.db` as default setting.

To create your own map, run:
```
roslaunch turtlebot3_slam_3d turtlebot3_rtabmap.launch
```

To navigate through your map use:
```
roslaunch turtlebot3_slam_3d turtlebot3_rtabmap.launch localization:=true
```