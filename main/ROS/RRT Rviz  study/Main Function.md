```
#include "rrt_planner/rrt_planner.h"

int main(int argv, char ** argc)
{
  ros::init(argv, argc, "rrt_planner");
  ros::NodeHandle node;
  new rrt_planner::RRTPlanner(&node);
}
```

# node handle as params
Yes, _passing a node handle_ to a class containing some algorithm implementation is a common practice in ROS. The node handle is an object that _provides access to the ROS system_, such as publishing and subscribing to topics, creating services, and accessing parameters.

In the main function of a ROS node, you typically initialize the ROS node using `ros::init()` and create a `NodeHandle` object to interact with the ROS system. Then, you can create an instance of your algorithm class and pass the `NodeHandle` object to its constructor. This allows your algorithm class to access the ROS system and perform the required tasks, such as publishing or subscribing to topics.

In the code you provided, the `RRTPlanner` class is _initialized with a `NodeHandle` object_, which is used by the class to interact with the ROS system and perform the path planning algorithm.



# Python version
## Python memory management
In Python, memory management is handled by the **Python interpreter itself, and the language provides built-in garbage collection**.

Python uses a technique called _reference counting_ to keep track of objects in memory. When an object is created, it is assigned a reference count of 1. Whenever a new reference to the object is created, such as by assigning it to a variable or passing it as an argument to a function, the reference count is incremented. When a reference to the object is deleted, such as by reassigning the variable or when the function returns, the reference count is decremented. When the reference count reaches 0, the object is no longer accessible and its memory is automatically freed by the garbage collector.

Python also provides a few memory management tools such as the `sys.getsizeof()` function to get the size of an object in bytes, and the `gc` module which provides access to the garbage collector and allows for finer control over object lifecycle.

In general, Python developers do not need to worry about memory management as much as C++ developers do, but it is still important to understand how it works to avoid issues such as memory leaks and excessive memory usage.
Python main function
```
#!/usr/bin/env python

import rospy
from rrt_planner import RRTPlanner

if __name__ == '__main__':
    rospy.init_node('rrt_planner')
    rrt = RRTPlanner()
    rospy.spin()
```
The `if __name__ == '__main__':` statement ensures that the code inside the block only runs if the script is being executed as the main program and not being imported as a module. 
The `rospy.init_node()` function initializes the ROS node with the given name "rrt_planner". 
Then an instance of the `RRTPlanner` class is created using the `rrt = RRTPlanner()` syntax. 
Finally, the `rospy.spin()` function is called, which **enters into a loop and keeps the node running until it is shutdown**.

in Python, you can simply **create an instance of a class and hold it in a variable without using any explicit memory management commands**. Python has an automatic memory management system called garbage collector that automatically deallocates memory that is no longer being used. Therefore, there is no need to manually deallocate memory as in C++.