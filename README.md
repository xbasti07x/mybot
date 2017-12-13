First development version of the driverless rc-car. This project is a changed version of the mybot project from http://www.moorerobots.com/blog/post/1 .In this iteration the car is configured with a differential drive and ros_naigation stack. 
To drive it doesnt need a map. If u want to use the map activate the amcl node in the amcl_demo.launch file.
 
**Driving without Map** 

In Terminal 1, launch the Gazebo world

roslaunch mybot_gazebo mybot_world.launch


In Terminal 2, start map building
- Navigation stack has to be installed: sudo apt-get install ros-kinetic-navigation

roslaunch mybot_navigation amcl_demo.launch


In Terminal 3, launch rviz

roslaunch mybot_description mybot_rviz_amcl.launch
 
 
**Creating the Map**

Run the following commands below. Use the teleop to move the robot around to create an accurate and thorough map.

In Terminal 1, launch the Gazebo world

roslaunch mybot_gazebo mybot_world.launch

In Terminal 2, start map building

roslaunch mybot_navigation gmapping_demo.launch


In Terminal 3, launch rviz and set the following parameters:

roslaunch mybot_description mybot_rviz_gmapping.launch


In Terminal 4, start teleop

roslaunch mybot_navigation mybot_teleop.launch


**Saving the Map**

In Terminal 5, save the map to some file path

rosrun map_server map_saver -f ~/mybot_ws/src/mybot_navigation/maps/test_map


**Loading the Map**

Close all previous terminals and run the following commands below. Once loaded, use rviz to set navigation waypoints and the robot should move autonomously.

In Terminal 1, launch the Gazebo world

roslaunch mybot_gazebo mybot_world.launch


In Terminal 2, start map building

roslaunch mybot_navigation amcl_demo.launch


In Terminal 3, launch rviz

roslaunch mybot_description mybot_rviz_amcl.launch
