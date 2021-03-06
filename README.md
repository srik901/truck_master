## Predictive Control for Autonomous Articulated Vehicles ##

<img align="right" height="250px"  src="https://github.com/ArticulatedControl17/truck_master/raw/master/truck.gif">

A Bachelor's Thesis about self driving trucks done at [Chalmers University of Technology](https://www.chalmers.se/) in 2017. In collaboration with [Volvo Trucks](https://volvotrucks.com). 

The result of the project was a control strategy for guiding a model semi-trailer truck through a narrow course consisting of several 90-degree turns and a roundabout. The truck is controlled with a RaspBerry Pi via WiFi. [ROS](http://www.ros.org/) (Robot Operating System) was used to build the system. Check out some videos at our [Youtube playlist](https://www.youtube.com/watch?v=i-70Hk7HvNk&index=1&list=PLmeEzXK5FpZj2EiShdH6pAmLi_jEV-3rX). Also check out the [project presentation](https://drive.google.com/open?id=18BYSGDIeqZW2vUmPet3hjSPzdr5snoopvyuz0NMTTRA) and the [project report](https://github.com/ArticulatedControl17/truck_master/raw/master/Project_report.pdf)


Link to the 2018 project, that builds on this one: https://github.com/ArticulatedControl18

## Try out the project ##


<img align="right" height="340px" src="https://github.com/ArticulatedControl17/truck_master/raw/master/pathplanning.gif">

If you'd like to try out the project in a simulation environment, then follow the instructions below.
System requirements: Ubuntu 16+

### Installation ###

* Download this [script](https://github.com/ArticulatedControl17/truck_master/blob/master/installation.sh) (updated 2018-01-22), which downloads ROS, creates a new catkin workspace and clones down all the repositories you need. If you don't need to do all this, just comment out the lines you don't want to run

    * Put the file where you want to create the new workspace and **source** it (just running it won't work)
     
          cd path/to/installation     

          source ./installation.sh


### How to run the simulator ###
* `roslaunch truck_master master.launch`
* Use the "2D Nav Goal" tool to set the goal.
    * Watch as the pathplanning does it's thing and the truck starts to move :)
* To set the position and direction of the truck, use the "2D Pose Estimate" tool
* To put subgoals use the "Publish Position" tool
* Add obstacles by focusing the window with the pyplot and press the number of the obstacle you want to add. (on the keyboard)
    * Watch as the rviz map is updated :)
* If the pathplanning seems to be stuck in an infinite loop you may have to kill the node (or just restart everything).
    * `rosnode kill path_planning`
    * Remove all obstacles
    * `rosrun path_planning path_planning_node.py`
