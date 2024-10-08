# RPLIDAR with Camera and SLAM Integration

This repository is a modified version of the original [slamtech/rplidar](https://github.com/Slamtec/rplidar) project. It extends the functionality by integrating a camera, adding SLAM (Simultaneous Localization and Mapping) nodes, and generating occupancy grids via separate nodes.

## Features
- **LIDAR and Camera Integration**: Combines data from LIDAR and camera for enhanced mapping.
- **SLAM Nodes**: Added SLAM capabilities using custom nodes.
- **Occupancy Grid Generation**: Produces occupancy grids in real-time using separate nodes.

## Added Nodes
The following new nodes have been implemented:

1. **lidar_map_node.cpp**: 
   - Handles mapping using LIDAR data to create a 2D map.
   
2. **igvc_slam_node.py**: 
   - SLAM node responsible for fusing sensor data (LIDAR, camera, etc.) and building the map.
   
3. **cv_to_map2.py**: 
   - Processes camera images and converts them to mapping information used for SLAM.

## Installation

1. Clone this repository:
    ```bash
    git clone https://github.com/Rgopikrishnan18/IGVC-test-dir.git
    cd IGVC-test-dir
    ```

2. Install dependencies:
    - Ensure you have the required ROS 2 packages installed:
      ```bash
      sudo apt install ros-<distro>-rplidar-ros
      sudo apt install ros-<distro>-cv-bridge
      ```

3. Build the workspace:
    ```bash
    colcon build
    ```

4. Source the workspace:
    ```bash
    source install/setup.bash
    ```

## Usage

To run the nodes, use the following commands:

1. **LIDAR Mapping Node**:
    ```bash
    ros2 run rplidar_ros lidar_map_node
    ```

2. **SLAM Node**:
    ```bash
    ros2 run rplidar_ros igvc_slam_node
    ```

3. **Camera to Map Node**:
    ```bash
    ros2 run rplidar_ros cv_to_map2
    ```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Original [slamtech/rplidar](https://github.com/Slamtec/rplidar) repository.
- ROS community for providing extensive tools and support.
