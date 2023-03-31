# Public and Private
The reason for separating the member functions into public and private sections is to enforce encapsulation and to control access to the class members.

The _public_ section of a class contains the member functions that are intended to be accessed from outside the class, either by other parts of the program or by other classes. These functions provide an interface to the class functionality and allow the user to interact with the class in a controlled and predictable way.

On the other hand, the private section of a class contains the member functions and variables that are intended to be used only within the class itself. These members are not accessible from outside the class, and are used to implement the class functionality and ensure the correctness of the class behavior.

In the case of the `RRTPlanner` class, the public member functions such as `makePlan()` and `initialize()` are the interface through which other parts of the program or other classes can interact with the `RRTPlanner` class. The private member functions such as `generateRandomPoint()` and `findNearestPoint()` are used internally by the class to implement its behavior and are not intended to be accessed from outside the class. By separating the member functions into public and private sections, the `RRTPlanner` class ensures that its behavior is consistent and predictable and that its internal implementation details are hidden from the rest of the program.


# nh_ and private_nh_
```
RRTPlanner::RRTPlanner(ros::NodeHandle * node)
: nh_(node),
  private_nh_("~"),
  map_received_(false),
  init_pose_received_(false),
  goal_received_(false)
```
`nh_` and `private_nh_` are both instances of `ros::NodeHandle` and they both point to the same `NodeHandle` object that was created in the `main` function and passed as a pointer to the constructor.

The difference is that `private_nh_` is **created with a "~" prefix**, which means that any parameter that is looked up with this `NodeHandle` will be searched for in the node's **private namespace**. This allows the node to have its own private parameters, which can be set independently of the global parameters of the node.

# ros::NodeHandle::param() method
```
private_nh_.param<std::string>("map_topic", map_topic, "/map");
private_nh_.param<std::string>("path_topic", path_topic, "/path");
```
These two lines are using the `ros::NodeHandle::param()` method to _get the values_ of the ROS parameters `map_topic` and `path_topic`.


In particular, `private_nh_.param<std::string>("map_topic", map_topic, "/map")` is getting the value of the `map_topic` parameter from the private node handle `private_nh_`. **If `map_topic` is not set, it defaults to the string `"/map"`**.

Similarly, `private_nh_.param<std::string>("path_topic", path_topic, "/path")` is getting the value of the `path_topic` parameter from the private node handle `private_nh_`. If `path_topic` is not set, it defaults to the string `"/path"`.

Overall, these lines are retrieving parameter values from the ROS parameter server and storing them in the local variables `map_topic` and `path_topic`, respectively.

The `private_nh_.param()` function retrieves the parameter value from the ROS parameter server and stores it in the specified variable. In this case, **`map_topic` and `path_topic` are strings that are declared earlier in the code, and they will be assigned the values retrieved from the ROS parameter server by the `private_nh_.param()` function.**


In the launch file of the `rrt_planner` package, these parameters are set using the `<rosparam>` tag:
`<rosparam command="load" file="$(find rrt_planner)/cfg/config.yaml"/>
`
And the value of map_topic and path_topic comes from the _config.yaml_ file

# 