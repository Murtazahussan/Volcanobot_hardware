# Volcanobot_Hardware
###>>>> Real-World Hardware Based Real-Time 3D Mapping Using 2 RP-Lidars in Vertical and Horizontal <<<<###

### Dedication

(•) Specially this project is dedicated to my parants S.Mujahid hussain (My Father) and Kaneez Fatima Rizvi (My Mother), Institute of Industrial Electronics Engineering: IIEE and to the students of IIEE.

# Building For Hardware Setup

### 1) Proposed Solution

(•) Main theme of “SLAM BASED 3D MAP BUILDING USING 2 LOW COST 2D LASER SCANNERS (RPLIDAR A1)” is an orthogonal combination of two RP-Lidar 2D laser scanners which has beed used on slam’s vehicle to build real-time 3D point cloud map of the explored region.

![image](https://user-images.githubusercontent.com/122727165/213647514-308d9fa9-696b-4b9e-b3d3-d3831a972ef5.png)

### 2) Real Robot Harware Setup

(•) The rover selection is customize based on 4WD mobile platform model. There are two sections where we can mount our additional hardware. These sections may be called as lower section and upper section.

![image](https://user-images.githubusercontent.com/122727165/213649634-c42d7a74-7a51-4aee-b0e1-a57e40e96467.png)

(•) Additionally, for the support of LIDARs, an acrylic stand in orthogonal shape has been designed and fabricated. Two surfaces have been developed on the stand 

![image](https://user-images.githubusercontent.com/122727165/213650407-4ea27207-b368-406d-a75b-a56d3bcb6197.png)
![image](https://user-images.githubusercontent.com/122727165/213650438-49017536-533d-4882-8743-e34cab36ce77.png)

(•) Here, the use of 1000 Rpm encoder motors for getting the feedback from encoder for correct Rover's pose in the environment.

![image](https://user-images.githubusercontent.com/122727165/213650463-6cb6bc4f-6deb-4c1f-8bcd-3e4d9342c89f.png)
![image](https://user-images.githubusercontent.com/122727165/213650485-23970853-cd75-4a79-91bc-335eb83a9de2.png)

(•) The hardware connection from motor to arduino through motor driver ln298 as follows:

![image](https://user-images.githubusercontent.com/122727165/213760627-b648e309-7888-416d-98f4-fbb299c113c4.png)
![image](https://user-images.githubusercontent.com/122727165/213760680-6d45f9eb-48cc-4162-acbb-f77cc8e425e1.png)

(•) All hardware connections including raspberry-Pi 3 model B to arduino and rp-lidars as follows:

![image](https://user-images.githubusercontent.com/122727165/213656700-e2873a69-79a6-4ff9-9e3a-47c0bdd78ac3.png)
![image](https://user-images.githubusercontent.com/122727165/213656723-915c5efd-6ca7-4a2c-b339-04084feba87d.png)

### 3) Rover Connectivity and control

![image](https://user-images.githubusercontent.com/122727165/213664272-f49d39ca-9ed2-4906-8fbf-c38654482bd4.png)

### 4) Vertical Lidar Zero-Degree Transformation

(•) The objective of lidar’s zero degree transformation is to reduce length of lidar’s frame (reduction in the lidar’s frame, compact in size). Another objective is to increase the flexibility in lidar.

![image](https://user-images.githubusercontent.com/122727165/213665672-51ff5c2f-4e00-43bb-b33d-bd88795aa3d9.png)

![image](https://user-images.githubusercontent.com/122727165/213666829-adec00ae-6742-4b07-b07b-a121a4f92d35.png)
![image](https://user-images.githubusercontent.com/122727165/213666975-dd90533e-b048-41c9-847d-e517581c53b9.png)

# Working in brief

### 1) Installation in raspberry-Pi 3 model B

(•) The given link will be use for download ros image 

    https://learn.ubiquityrobotics.com/kinetic_pi_image_downloads

(•) after this image burn into your card and after first reboot user is UBUNTU and the password is also ubuntu, then connect raspberry to your network and coomunicate through ssh protocol.

    https://www.instructables.com/Using-RPlidar-With-Robot-Navigation/

(•) The above link use before step 5 only for roscore checking.

(•) after step 4 follow given link

    http://chaolong-chen blog.logdown.com/posts/696217-cmake

(•) After this follow given link for installation of arduino 

    https://www.arduino.cc/en/software

(•) After this follow given link for installation of rosserial

    https://www.youtube.com/watch?v=nyaF6BG4bT4&t=403s&ab_channel=wansnap

##### Installation For Rp-lidar driver
 
    cd catkin_ws/src
 
    https://github.com/Murtazahussan/Volcanobot_hardware.git
 
    cd ..
 
    source devel/setup.bash

##### Installation For Hector-SLAM Package
 
    cd catkin_ws/src
 
    https://github.com/tu-darmstadt-ros-pkg/hector_slam.git
 
    cd ..
 
    source devel/setup.bash

##### Installation For IRA_LASER_TOOLS Package

clone follow package into your workspace

    cd catkin_ws/src

    https://github.com/Murtazahussan/ira_laser_tools.git

NOTE: Above command produce merged node of point-cloud whose name is merged_cloud for 3D point-cloud

    cd ..
 
    source devel/setup.bash

##### For Master-Slave Communication

    https://www.youtube.com/watch?v=pJ_LL4gGGEM&t=2s&ab_channel=UDMRoboticsLAB

### 2) Topics Publish By Arduino on ROS

(•) Starting from the low-level control the Robot uses an Arduino UNO takes cmd_vel from the raspberry-Pi 3 model B via ros-serial via USB. The Arduino is also responsible for reading the encoder values and publishing it back to the raspberry-Pi 3 model B.

##### Topics published and subscribed by Arduino

    /cmd_vel

    /right_ticks

    /left_ticks 

(•) I have used ln298 Motor driver for controlling the Dc motors with encoders.

(•) The Motor driver is connected to Arduino via UART (Tx,RX).4 such motor drivers where used to control the 4 motors and each motors where addresed using a unique slave-id set via jumper pins.

(•) The main advantage of using this motors were that only 3 wires (Tx,Rx,Gnd) was required to control all the 4 motors,vary its speed and read the encoder values.

https://user-images.githubusercontent.com/122727165/213761161-ae8d6e3d-2bcf-4883-be68-761befac182e.mp4

(•) The High level control is raspberry-Pi 3 model B which runs on ubuntu 16.04 with ROS kinetic installed.

(•) The Lidar is also connected to the raspberry-Pi 3 model B via Usb and the whole system is powered using 5v from a power bank of 10000 mah to power the raspberry-Pi 3 model B.

### 3) ROS Setup for Mapping

(•) The arduino publishes the encoder ticks into the raspberry-Pi 3 model B via ros-serial which are subscribed by the differential_drive package and publishes /odom as well as Tf (odom -> base_footprint).

(•) The Rp-Lidar package is responsible for publishing the both LaserScans as /scan /vertical_scan data along with Tf (base_link -> laser)

##### Tf Tree

(•) With the Robot Model

![image](https://user-images.githubusercontent.com/122727165/213768818-365b36a0-e132-44ad-938d-5a85aa9bd95b.png)

### 4) Real Robot Commands Setup and Executions 

(•) firstly connect raspberry-Pi 3 model B to laptop using master-slave communication then connect ssh communication through following command:

    ssh ubuntu@ubiquityrobot.local

(•) secondly connect horizontal lidar then vertical and in last connect arduino from raspberry-Pi 3 model B otherwise terminal shows port error

    roslaunch rplidar_ros view_rplidar.launch

    roslaunch rplidar_ros 123.launch

    cd catkin_ws/src

    source /opt/ros/kinetic/setup.bash

    cd 

    rosrun rosserial_python serial_node.py _baud:=115200 _port:=/dev/ttyUSB2

                                    OR 

    rosrun rosserial_arduino serial_node.py _port:=/dev/ttyUSB0 _baud:=115200

    rosrun teleop_twist_keyboard teleop_twist_keyboard.py

    roslaunch ira_laser_tools laserscan_multi_merger.launch

    roslaunch hector_slam_launch tutorial.launch

NOTE: Above command execution rviz open and it will shows the real lidars readings.

# Volcanobot Hardware Real-Time 3D Point-Cloud Generation Output

(•) 2D Grid map generation with Rover pose

![image](https://user-images.githubusercontent.com/122727165/213791901-64e4a7eb-5c24-40e8-9671-6213fb291c0f.png)
![image](https://user-images.githubusercontent.com/122727165/213791940-3952b991-a41d-48a7-90ac-046ef7d32eaf.png)

(•) Real-Time 3D point-cloud:

![image](https://user-images.githubusercontent.com/122727165/213790477-e55cc953-ebd9-4458-87d2-6a8b8800f641.png)
![image](https://user-images.githubusercontent.com/122727165/213790505-5554246e-13c8-4aee-b002-374ebf8f4494.png)


![image](https://user-images.githubusercontent.com/122727165/213790405-203974d1-1e0d-44d8-a7fc-996a33a3f758.png)
![image](https://user-images.githubusercontent.com/122727165/213790430-7e09480b-960e-4bcf-b302-dfc9de8cfd2c.png)

# FINAL HARDWARE WORKING VIDEO OF REAL-TIME 3D Point Cloud Generation

https://user-images.githubusercontent.com/122727165/213859113-7919e822-3ea8-4c50-9b15-21876d4ad5ad.mp4


https://user-images.githubusercontent.com/122727165/213870952-19992e87-2648-41b0-a5be-af8c854312f2.mp4


#####################>>>>>>>> Best Of Luck IIEEIANS <<<<<<<<#####################


















