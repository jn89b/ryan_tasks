# Ros2 Tasks
- Ubuntu 22.04:
    - I need you to download ROS2 Humble
    - https://docs.ros.org/en/humble/index.html
    - Make a ros2_ws 
    - In ros2_ws/src I want you to download apriltag_ros2
    - https://github.com/christianrauch/apriltag_ros
- I want you to publish apriltag detections to a topic and subscribe to it in a different node
- I want you to log the data and record it in a csv file 
with true position estimate vs the estimated topic position 
    - Here is a useful tool to check data or log data:
        - https://plotjuggler.io/ 
        - Talk to Jordan 
- Get the mean and uncertainty of the data 
- Ideally we want to detect the tags about 75 meters away 