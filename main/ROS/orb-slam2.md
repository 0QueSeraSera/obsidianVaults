[[SLAM-ROS2 code]]
****
# moncular-slam-node.hpp
class `MonocularSlamNode` inheritated from `rclcpp::Node`

# moncular-slam-node.cpp
`MonocularSlamNode(ORB_SLAM2::System* pSLAM);`
http://wiki.ros.org/orb_slam2_ros
ORB_SLAM2 is a ros2 node
![[Pasted image 20230110210643.png]]

subscribe to ImageMsg
![[Pasted image 20230110211610.png]]
**"camera" is the topic name**

# USAGE
![[Pasted image 20230110211907.png]]
