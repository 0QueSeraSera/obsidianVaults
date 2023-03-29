`roslaunch rrt_planner rrt_planner.launch`

```
<launch>
    <arg name="rviz_config" default="$(find rrt_planner)/cfg/rrt_planner.rviz"/>
    <arg name="map_file" default="$(find rrt_planner)/cfg/map.yaml"/>

    <rosparam command="load" file="$(find rrt_planner)/cfg/config.yaml"/>

    <node type="rviz" name="rviz" pkg="rviz" args="-d $(arg rviz_config)"/>
    <node name="map_server" pkg="map_server" type="map_server" args="$(arg map_file)"/>
    <node type="rrt_planner_node" name="rrt_planner" pkg="rrt_planner" output="screen"/>
</launch>
```
# Package and Node naming
In the context of ROS, a **package** is a collection of ROS nodes, libraries, configuration files, and other resources that are grouped together for a specific purpose. In this case, the _package name is "rrt_planner"_.

The "node" in ROS refers to a process that performs computation. A ROS node can publish and subscribe to messages on a ROS topic, and can provide or use ROS services. In this case, the "rrt_planner_node" is a custom node defined in the "rrt_planner" package that uses the RRT algorithm to plan a path.

The _"name" argument_ in the launch file specifies **the name of the node that will be launched**, and the **"pkg" argument specifies the name of the package where the node is located**. In this case, the "name" argument is set to "rrt_planner", which matches the name of the custom node defined in the "rrt_planner" package. The "pkg" argument is also set to "rrt_planner", which specifies the package where the custom node is located.

In summary, the naming of the node and the package in this launch file are consistent with the implementation of the RRT algorithm in the "rrt_planner" package.

# launch file and command
## roslaunch command
Sure! Let me explain each argument in the `roslaunch` command:
-   `roslaunch`: This is the command to launch a ROS launch file.
-   `rrt_planner`: This is the _name of the ROS package_ containing the launch file.
-   `rrt_planner.launch`: This is the _name of the launch file_ to be launched.
The package name is specified in _package.xml_ under _src folder_
## launch file
-   `map_file:=$(find rrt_planner)/cfg/map.yaml`: This sets the value of the `map_file` argument used in the launch file. The `$(find rrt_planner)` command finds the directory path of the `rrt_planner` package and adds it to the argument value. So, the resulting `map_file` argument value is the path to the `map.yaml` file located in the `cfg` directory of the `rrt_planner` package.
-   `rviz_config:=$(find rrt_planner)/cfg/rrt_planner.rviz`: This sets the value of the `rviz_config` argument used in the launch file. The `$(find rrt_planner)` command finds the directory path of the `rrt_planner` package and adds it to the argument value. So, the resulting `rviz_config` argument value is the path to the `rrt_planner.rviz` configuration file located in the `cfg` directory of the `rrt_planner` package.

The `output="screen"` argument in the `node` tag of the launch file tells ROS to display the output of the `rrt_planner` node in the console.

# arg and rosparam
Both `arg` and `rosparam` are used to _provide parameter values_ to a launch file. However, they have different use cases and behaviors:
-   `arg`: This is short for "argument" and is used to pass parameters into a launch file **from the command line** or **from another launch file**. `arg` parameters **can have default values**, like in the example you provided: `<arg name="rviz_config" default="$(find rrt_planner)/cfg/rrt_planner.rviz"/>`. This line sets the `rviz_config` argument to a *default value* of `$(find rrt_planner)/cfg/rrt_planner.rviz`, which means that if the argument is not set when the launch file is executed, this default value will be used. You can override the default value by **setting the argument when you run the launch file**, like this: `roslaunch my_package my_launch_file.launch rviz_config:=path/to/my/config.rviz`.
    
- `rosparam`: This is used to _set parameter values in the ROS parameter server_, which is a **central repository for parameter values that nodes can access**. `rosparam` can load values from a file (using the `command="load"` attribute), or it can set parameter values directly using the `param` attribute. In the example you provided, the `rosparam` command is used to load a YAML configuration file: `<rosparam command="load" file="$(find rrt_planner)/cfg/config.yaml"/>`. This line loads the parameter values defined in `$(find rrt_planner)/cfg/config.yaml` into the ROS parameter server. The loaded parameter values can be accessed by nodes in the launch file or in other launch files that are executed after this one.
    
In general, you can use `arg` to _set parameters that may vary from launch to launch_, like file paths or numerical values that depend on the environment. On the other hand, you can use `rosparam` to set parameters that are more **static and are used by multiple nodes** in your system.



# Map Generation
The occupancy grid map message is typically generated by a mapping or SLAM algorithm, such as GMapping, Hector SLAM, or Cartographer. These algorithms take sensor data, such as laser scans or RGB-D camera images, and use them to build a map of the environment.

In the case of the example we discussed earlier, the occupancy grid map message is **loaded from a YAML file** using the `map_server` node. This is a simple way to load a pre-existing map for testing purposes, without the need for mapping or SLAM algorithms.

The YAML file specifies the location of the map image file and its resolution, which are used to generate the occupancy grid map message. The `map_server` node then publishes this message on the `/map` topic, which can be subscribed to by other nodes, such as the path planning node.

## Map server node
Yes, the `map_server` node provides the capability to _read a map from an image file and publish it as a ROS message_. Specifically, it reads a map from an image file in one of the supported formats (e.g., BMP, PNG, PGM, etc.), converts it to an occupancy grid map, and publishes it on a ROS topic.

The `map_server` node has a ROS service called `map_server/load_map` that loads a map from a file and returns a `nav_msgs/OccupancyGrid` message. The `map_server` node can also be used to save a map to a file using the `map_server/save_map` service.

This makes it very easy to load and use maps in ROS applications. The `map_server` node is often used in conjunction with other nodes that perform localization, path planning, or other tasks that require access to a map.
