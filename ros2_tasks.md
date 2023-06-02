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
    - Go to the motion capture room and there should be a big vinyl roll and if you unroll it should be a big apriltag 
    - If we cant find it consider making one 

# Things to troubleshoot
- Fix your source install/setup.bash in your bashrc 
  - Talk to Jordan, Teddy, or Chris 

# To run ros2 nodes do this
```
ros2 run 
```

# Ros2 apriltag ros2 with intel realsense 
Make sure to have things sourced!
Run the ros2 intel real sense node
```
ros2 launch realsense2_camera rs_launch.py
```

**On another terminal run the realse ros2 node**
Remap this to our real sense camera
```
ros2 run apriltag_ros apriltag_node --ros-args \
    -r image_rect:=/camera/image \
    -r camera_info:=/camera/camera_info \
    --params-file `ros2 pkg prefix apriltag_ros`/share/apriltag_ros/cfg/tags_36h11.yaml
```

Here is our parameters we are going to use
```
ros2 run apriltag_ros apriltag_node --ros-args \
    -r image_rect:=/camera/color/image_raw \
    -r camera_info:=/camera/color/camera_info
 \
    --params-file `ros2 pkg prefix apriltag_ros`/share/apriltag_ros/cfg/tags_36h11.yaml
```

On another terminal 