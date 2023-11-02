---
title: "ros1 ros2 bridge로 연결하기"
excerpt_separator: "<!--more-->"
categories:
  - Study
tags:
  - ROS
---

사전에 ROS1과 ROS2가 설치되었다고 가정

bridge package 설치  
$ sudo apt install ros-dashing-ros1-bridge

터미널마다 ros1을 쓸지 ros2를 쓸지 결정해야하므로 간단하게 alias로 저장해두자  
echo "alias ros11='source /opt/ros/noetic/setup.bash'" >> ~/.bashrc  
echo "alias ros22='source /opt/ros/galactic/setup.bash'" >> ~/.bashrc

실행 방법  
terminal 1 (ros1)  
$ ros11  
$ roscore  
terminal 2 (ros2)  
$ ros11  
$ ros22  
$ ros2 run ros1_bridge dynamic_bridge --bridge-all-topics  
or
$ ros2 run ros1_bridge dynamic_bridge

간단 테스트  
ros1 terminal  
$ rosrun rospy_tutorial talker  
ros2 terminal  
$ ros2 run demo_nodes_cpp listener  
talker와 listener를 바꿔서도 해보자.
