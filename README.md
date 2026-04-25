# Smart Vehicle

Parent repository for a functional Carla-ROS Smart Vehicle simulation. The repository integrates a CARLA simulation package for a cooperative vehicle, a custom robotic description of the vehicle for the proper generation of a standardized transform tree, a common interfaces package to manage and formalize traffic information to provide context for decision-making within the appropriate Operational Design Domain (ODD), and, finally, a high-definition map management engine package for the virtual localization and planning system.

## Requirements

* **OS:** Ubuntu 22.04 LTS
* **ROS:** ROS2 Humble
* **Dependencies:** Ensure all individual package dependencies are met (*Check each submodule*).

## Submodules

* **`carla_vehicle`**: Implements a custom bridge between Carla and ROS2 with standard ROS2 configurations.
* **`ego_vehicle_description`**: Implements a robot description of a custom ego vehicle for proper `tf` tree generation (ROS compatible).
* **`map`**: HD Map engine for localization and planning features.
* **`ros_interfaces`**: Folder to store Traffic Scene implementation with custom Road, Perception, Awareness, Behavior, and Cooperation messages.

## Installation

```bash
cd ros2_ws
git clone https://github.com/dayaguec/smart_vehicle.git

# Enter the cloned repository
cd smart_vehicle
git submodule update --init --recursive
./update_respos.sh

# Enter the map submodule to initialize its own nested submodules
cd map
git submodule update --init --recursive

# Return to the workspace root to build
cd ../..
colcon build
