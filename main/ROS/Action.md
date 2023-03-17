[[ROS2]]
****
# Explaination
Actions are one of the communication types in ROS 2 and are intended for _long running tasks_. They consist of three parts: **a goal, feedback, and a result**.
![[Pasted image 20230111160138.png]]

Actions use a client-server model, similar to the publisher-subscriber model (described in the [topics tutorial](http://docs.ros.org/en/rolling/Tutorials/Beginner-CLI-Tools/Understanding-ROS2-Topics/Understanding-ROS2-Topics.html)). An “action client” node sends a goal to an “action server” node that acknowledges the goal and returns a stream of feedback and a result.


# Definition and Building
![[Pasted image 20230111160356.png]]

-   A _request_ message is sent from an action **client** to an action **server** initiating a new goal.
-   A _result_ message is sent from an action server to an action client when a goal is done.
-   _Feedback_ messages are _periodically_ sent from an action server to an action client with updates about a goal.
![[Pasted image 20230111160613.png]]