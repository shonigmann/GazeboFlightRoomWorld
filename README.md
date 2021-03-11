# GazeboFlightRoomWorld
This repository contains models and world files to generate an indoor flight room environment in Gazebo simulator, roughly based on the Stanford Flight room. 

The included CAD was largely modelled using the image references here: https://stanfordflightroom.github.io/
Models can be expected to be visually representative, but no claims are made of dimensional accuracy. 

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

## Visual Textures:
One of the applications being worked on in this environment involved visual navigation. To increase the number of visual features in the environment, without increasing the environment complexity, outer walls were textured with a set of vaguely representative, high resolution images to give the illusion of an expanded environment. This is suitable for feature based approaches (e.g. OrbSlam) but may cause more advanced algorithms to fail, as the objects in the background have no depth. 

Additionally, the visual SLAM algorithms being tested broke down in the presence of transparent obstacles (e.g. the netting or the windows). Transparent obstacles would appear as perfectly opaque to Gazebo's simulated depth sensor (which uses collision models), but transparent to the simulated camera (which uses separate visual models). The discrepancy led to some strange issues, and a work-around was to make the net and windows opaque, hence the second world file included. 

## Note:
The original world file was generated using the Solidworks to URDF exporter, which has the unpleasant side-effect of applying transformations to the mesh rather than to the URDF or SDF <pose> tags. This makes things a bit less intuitive to move around in the Gazebo environment. Apologies in advance if you want to move things around!    
