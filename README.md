# Merge 2D LiDAR

A comprehensive guide to merging two 2D LiDAR sensors using ROS2 packages.

## Installation
## 1. Clone Required Repositories
Begin by cloning the necessary repositories into your ROS2 workspace's src directory.

```
# Clone sllidar_ros2
git clone https://github.com/Slamtec/sllidar_ros2.git

# Clone ros2_laser_scan_merger
git clone https://github.com/mich1342/ros2_laser_scan_merger.git

# Clone pointcloud_to_laserscan
git clone https://github.com/ros-perception/pointcloud_to_laserscan.git
```
## 2. Switch Branch for `pointcloud_to_laserscan` Package
Ensure compatibility by switching the `pointcloud_to_laserscan` package to the `humble` branch.
```
cd pointcloud_to_laserscan

git checkout humble
```
## 3. Move `carver_lidar.launch.py` File
Move the `carver_lidar.launch.py` file to the `launch` directory within the `sllidar_ros2` package.

## 4. Build the Workspace
```
colcon build
```

## Running the Launch Files
After successfully building the workspace, you can launch the merged LiDAR setup.
Launch the LiDAR Node:
```
ros2 launch sllidar_ros2 carver_lidar.launch.py
```
Launch the Laser Scan Merger without RViz2 visualization:
```
ros2 launch ros2_laser_scan_merger merge_2_scan.launch.py
```
Launch the Laser Scan Merger with RViz2 visualization:
```
ros2 launch ros2_laser_scan_merger visualize_merge_2_scan.launch.py
```
The merge laserscan will be appear in `/scan` topic. You can use the topic for futher use.

## Acknowledgements
[Slamtec sllidar_ros2](https://github.com/Slamtec/sllidar_ros2)

[ros2_laser_scan_merger](https://github.com/mich1342/ros2_laser_scan_merger)

[pointcloud_to_laserscan](https://github.com/ros-perception/pointcloud_to_laserscan/tree/humble)