# Volcanobot_Hardware
###>>>> Real-World Hardware Based Real-Time 3D Mapping Using 2 RP-Lidars in Vertical and Horizontal <<<<###

### Dedication

Specially this project is dedicated to my parants S.Mujahid hussain (My Father) and Kaneez Fatima Rizvi (My Mother), Institute of Industrial Electronics Engineering: IIEE and to the students of IIEE.

# Building For Hardware Setup

### 1) Proposed Solutuin

Main theme of “SLAM BASED 3D MAP BUILDING USING 2 LOW COST 2D LASER SCANNERS (RPLIDAR A1)” is an orthogonal combination of two RP-Lidar 2D laser scanners which has beed used on slam’s vehicle to build real-time 3D point cloud map of the explored region.

![image](https://user-images.githubusercontent.com/122727165/213647514-308d9fa9-696b-4b9e-b3d3-d3831a972ef5.png)

### 2) Real Robot Harware Setup

The rover selection is customize based on 4WD mobile platform model. There are two sections where we can mount our additional hardware. These sections may be called as lower section and upper section.

![image](https://user-images.githubusercontent.com/122727165/213649634-c42d7a74-7a51-4aee-b0e1-a57e40e96467.png)

Additionally, for the support of LIDARs, an acrylic stand in orthogonal shape has been designed and fabricated. Two surfaces have been developed on the stand 

![image](https://user-images.githubusercontent.com/122727165/213650407-4ea27207-b368-406d-a75b-a56d3bcb6197.png)
![image](https://user-images.githubusercontent.com/122727165/213650438-49017536-533d-4882-8743-e34cab36ce77.png)

Here, the use of 1000 Rpm encoder motors for getting the feedback from encoder for correct Rover's pose in the environment.

![image](https://user-images.githubusercontent.com/122727165/213650463-6cb6bc4f-6deb-4c1f-8bcd-3e4d9342c89f.png)
![image](https://user-images.githubusercontent.com/122727165/213650485-23970853-cd75-4a79-91bc-335eb83a9de2.png)

The hardware connection from motor to arduino through motor driver ln298 as follows:

![image](https://user-images.githubusercontent.com/122727165/213656125-75168a0c-d541-4a4c-b023-47bfcdc13efb.png)
![image](https://user-images.githubusercontent.com/122727165/213656150-c2485c87-d0ee-42ce-8311-168da7f5e068.png)

All hardware connections including respberry-Pi 3 model B to arduino and rp-lidars as follows:

![image](https://user-images.githubusercontent.com/122727165/213656700-e2873a69-79a6-4ff9-9e3a-47c0bdd78ac3.png)
![image](https://user-images.githubusercontent.com/122727165/213656723-915c5efd-6ca7-4a2c-b339-04084feba87d.png)

### 3) Rover Connectivity and control

![image](https://user-images.githubusercontent.com/122727165/213664272-f49d39ca-9ed2-4906-8fbf-c38654482bd4.png)

### 4) Vertical Lidar Zero-Degree Transformation

The objective of lidar’s zero degree transformation is to reduce length of lidar’s frame (reduction in the lidar’s frame, compact in size). Another objective is to increase the flexibility in lidar.

![image](https://user-images.githubusercontent.com/122727165/213665672-51ff5c2f-4e00-43bb-b33d-bd88795aa3d9.png)

![image](https://user-images.githubusercontent.com/122727165/213666829-adec00ae-6742-4b07-b07b-a121a4f92d35.png)
![image](https://user-images.githubusercontent.com/122727165/213666975-dd90533e-b048-41c9-847d-e517581c53b9.png)

# Working in brief

### 1) Installation of ROS image in respberry-Pi 3 model B

https://learn.ubiquityrobotics.com/kinetic_pi_image_downloads


### 2) Installation For Hardware Setup
 
(.) cd catkin_ws/src
 
(.) https://github.com/Murtazahussan/Volcanobot_hardware.git
 
(.) cd ..
 
(.) source devel/setup.bash






















