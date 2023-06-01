# Mid360_simulation_plugin
Plugin for the simulation of the Livox Mid-360 based on the [official plugin](https://github.com/Livox-SDK/livox_laser_simulation)

Main changes:
- Support for ROS Noetic
- Support for Gazebo 11
- Support for the Livox ROS driver 2.0
- Support for custom message formats
- Corrected the distortion of the point cloud



This plugin relies on the Livox ROS driver to generate all the custom messages of the real Livox mid-360. We have included a version of the driver in this repo we are sure will work with the plugin. However, if you want to use a different version of the driver, you can do so by following the instructions in the official and up to date [Livox ROS driver repo](https://github.com/Livox-SDK/livox_ros_driver2).

## Build instructions

1. Clone this repo into your catkin workspace src folder.
```bash
cd ~/catkin_ws/src
git clone https://github.com/fratopa/Mid360_simulation_plugin.git
```
2. Build the Livox ROS driver.
```bash
cd ~/catkin_ws/src/Mid360_simulation_plugin/livox_ros_driver2
./build.sh ROS1
```
3. Build the plugin.
```bash
cd ~/catkin_ws
catkin build -DCMAKE_BUILD_TYPE=Release
```
## Run instructions

To verify that the plugin is working correctly you can run the minimal example:
```bash
roslaunch livox_laser_simulation test_pattern.launch
```
This will launch the plugin with a test pattern. You should see a point cloud in RViz and a gazebo window with a spinning laser.

## Citation

If you use this plugin in your research, please cite the following paper:

```
[Yesterday 11:21 AM] Cella Marco
@Article{isprs-archives-XLVIII-1-W1-2023-539-2023,
AUTHOR = {Vultaggio, F. and d'Apolito, F. and Sulzbachner, C. and Fanta-Jende, P.},
TITLE = {SIMULATION OF LOW-COST MEMS-LIDAR AND ANALYSIS OF ITS EFFECT ON THE PERFORMANCES OF STATE-OF-THE-ART SLAMS},
JOURNAL = {The International Archives of the Photogrammetry, Remote Sensing and Spatial Information Sciences},
VOLUME = {XLVIII-1/W1-2023},
YEAR = {2023},
PAGES = {539--545},
URL = {https://isprs-archives.copernicus.org/articles/XLVIII-1-W1-2023/539/2023/},
DOI = {10.5194/isprs-archives-XLVIII-1-W1-2023-539-2023}
}
```