# GazeboFlightRoomWorld
This repository contains models and world files to generate an indoor flight room environment in Gazebo simulator, roughly based on the Stanford Flight room. 

The included CAD was largely modelled using the image references here: https://stanfordflightroom.github.io/ 

Some models, such the desk chairs, were taken from grabcad.com and are credited in their respective model.config files. 

## Basic Use
To load the world in Gazebo, run the following command from the repository's root directory:
```
gazebo -v flight_room.world
```

Alternately, to run Gazebo in a ROS environment, a sample launch file can be run using:
```
roslaunch flight_room_gazebo.launch
```
