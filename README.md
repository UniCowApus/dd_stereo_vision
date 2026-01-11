Stereo Vision ROS 2 System

This is my distributed stereo vision pipeline built on ROS 2. It pushes real-time depth and perception processing as far my DDS and a home network will reasonably allow. About 30fps with 0.5 second visualization delay.

Overview

The system is split across two machines:

Edge Node (Raspberry Pi 5, ROS 2 Jazzy, Ubuntu 24.04 LTS)
Hosts the stereo camera drivers and publishes compressed image streams over the network.

Processing Node (Desktop, ROS 2 Humble, 22.04 Ubuntu) Runs fusion pipeline and publishes detections, confidence, bounding box, and object centers in camera frame.


This work started as an experiment using a dummy camera setup to run detections on a downloaded KITTI model until my camera and pi arrived yesterday. That original repository is messy, but it contains useful early work and could be cleaned up and documented further if reviewers are interested.

Repository Structure

fusion_processing_node/
This is where the majority of the meaningful implementation lives. Stereo fusion, synchronization, and processing logic are concentrated here.

edge_node/
Contains the camera-side integration code, along with a lightly documented but heartfeldt integration psychosis memoir.

Notes

With more time, this project would be more polished, better documented and tested, and easier to extend. That said, it was a genuinely enjoyable project to build, debug, and iterate on!

Last minute demo for proof of function:

![Epic demo](demo.webm)


During the code presentation, I can also provide:

Recorded rosbags

An interactive live demo
