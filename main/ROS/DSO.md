[[SLAM-ROS2 code]]
****
`camera.cpp` and `dso_ros.cpp`

# camera.cpp
## main()
create node **cam2image**
`auto node = rclcpp::Node::make_shared("cam2image");`

publish:
![[Pasted image 20230110212308.png]]
topic name: **topic**

subscribe:
![[Pasted image 20230110212459.png]]

video source:
![[Pasted image 20230110212807.png]]


# dso_ros.cpp
## main()
create node: "dsoimage"

subscribe: "image"
![[Pasted image 20230110213152.png]]
