---
title: "ros1 ros2 bridge로 연결하기"
excerpt_separator: "<!--more-->"
categories:
  - Study
tags:
  - ROS
---

사전에 ROS1과 ROS2가 설치되었다고 가정

bridge package 설치 (ros2 version에 따라 설치해야함, 예제는 galactic)  
$ sudo apt install ros-galactic-ros1-bridge

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

동일 route내에서 ROS_DOMAIN_ID 만 맞으면 다른 pc ros2와도 간단히 연결 된다.  
연결하고자하는 pc의 id 숫자를 모두 동일하게 해주자 (정확히는 각 터미널 마다)  
$ export ROS_DOMAIN_ID=숫자  
현재 ros 설정 상태 보는법  
$ printenv | grep ROS
