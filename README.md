# MYNTEYE_ROS_BRIDGE

## Run the mynteye docker
*Obs:* The camera should be plugged

```Bash
chmod +x Docker/mynteye.sh
./Docker/mynteye.sh

```

Navigate your home and clone the mynteye [repo](https://github.com/Brazilian-Institute-of-Robotics/MYNT-EYE-S-SDK) were you want

```Bash
sudo apt update
cd <sdk>
make init
make ros
source wrappers/ros/devel/setup.bash

```

To execute the mynteye node

```Bash
roslaunch mynt_eye_ros_wrapper mynteye.launch

```

## Execute the ROS_BRIDGE

```Bash
chmod +x Docker/docker-bridge.sh
./Docker/docker-bridge.sh

# Inside the docker execute:
source /opt/ros/noetic/setup.bash
source /opt/ros/foxy/setup.bash
export ROS_MASTER_URI=http://localhost:11311
export ROS_DOMAIN_ID=<ros ID>
ros2 run ros1_bridge dynamic_bridge --bridge-all-1to2-topics

```
