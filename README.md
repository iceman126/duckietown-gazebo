# Duckietown Environment and Duckiebot in gazebo

With this folder, you can run duckietown environment and control robot with gazebo.

## Install Depencencies

Requirements:
- Python 3
- ROS Melodic
- Gazebo 9
- Catkin_tools
- Catkin_pkg

**NOTE:  To build successfully, maybe you need to install a lot ros packages. Based on the error message, use ```sudo apt-get install ros-melodic-packagename```.**

## Install

### Install Catkin from source (the version on pip doesn't work)
- Go to instructions at [https://catkin-tools.readthedocs.io/en/latest/installing.html#installing-from-source]

### Setup Duckietown environment in gazebo
- Clone this repo & go to the directory
- `source /opt/ros/melodic/setup.bash`
- `catkin build`
- `source devel/setup.bash` or `source devel/setup.zsh`
- `cd src/duckietown_gazebo`
- `source env_gazebo.sh`
- `cd ..`
- `./run_gazebo.sh`
- You should be able to see a Duckiebot in Duckietown in gazebo.

In gazebo, shortcut "Ctrl+T" can call out "Gazebo: Topic Selector" window. Then click topic ```/gazebo/default/mybot/chassis/camera1/image```under ```gazebo.msgs.ImageStamped```, a camera window of dockiebot will show up.

You can also control robot through publish messege to topic with command ```rostopic pub /cmd_vel geometry_msgs/Twist "linear:
  x: 0.2
  y: 0.0
  z: 0.0
angular:
  x: 0.0
  y: 0.0
  z: 0.1"``` or ```./run_cmd```

**Note:** When loading some tracks, there might be an error message `[Err] [InsertModelWidget.cc:405] Missing model.config for model "/home/iceman126/duckietown-gazebo/src/duckietown_gazebo/models/rubber_duck"`. We are not sure this is would be a problem, since there's another model called `gazebo_duck` in the directory and the duckietown environment looks fine.

**TODO: complete the list of depencencies to install.**

```
sudo apt-get install \
ros-kinetic-xacro

# Python packages
pip install \
catkin_pkg \
catkin-tools \
defusedxml \
pyzmq \
rospkg \
pygazebo==3.0.0-2014.1
```






